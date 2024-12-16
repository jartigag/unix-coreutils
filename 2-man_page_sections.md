---
date: 2024-12-15
source: "Bite Size Linux" (Julia Evans)
---
# man page sections

- man pages are split up into 8 sections
  `man 2 read` means "get me the man page for read from section 2".
- There's both a program called "read" and a system call called "read",
  so `man 1 read` gives you a different man page from `man 2 read`.
- If you dont' specify a section, man will look through all the sections and show the first one it finds.

1. programs:

```bash
man grep
man ls
```

2. system calls:

```bash
man sendfile
man ptrace
```

3. C functions:

```bash
man printf
man fopen
```

4. devices:

```bash
man null # for /dev/null docs
```

5. file formats:

```bash
man sudoers # for /etc/sudoers
man proc    # files in /proc
```

6. games:

```bash
# not super useful
man sl
```

7. miscellaneous:

```bash
# explains concepts!
man 7 pipe
man 7 symlink
```

8. sysadmin programs:

```bash
man apt
man chroot
```
