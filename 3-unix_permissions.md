---
date: 2024-12-16"
source: "Bite Size Linux" (Julia Evans)
---
# unix permissions

- There are 3 things you can do to a file:
  - **r**ead
  - **w**rite
  - e**x**ecute

- `ls -l file.txt` shows you permissions. Here's how to interpret the output:

  ```bash
  rw-               rw-                 r--         bork   staff
  bork (user) can   staff (group) can   anyone can
   read & write      read & write        read
  ```

- File permissions are 12 bits:

  ```txt
             user   group   all
  000         110     110   100
  ^setuid
   ^setgid
  ```

- For files:

  ```txt
  r = can read
  w = can write
  x = can execute
  ```

- For directories, it's approximately:

  ```txt
  r = can list files
  w = can create files
  x = can `cd` into and access files
  ```

- 110 in binary is 6, so:

  ```txt
  rw- r-- r-- = 110 100 100 = 6 4 4
  ```

  `chmod 644 file.txt` means "change the permissions to `rw- r-- r--`".

- `setuid` affects executables:

  ```bash
  $ ls -l /bin/ping
  rws r-x r-x root root
    ^this means ping always runs as root
  ```

- `setgid` does 3 different unrelated things for executables, directories and regular files.
