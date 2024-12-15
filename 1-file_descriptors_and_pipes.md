---
date: 2024-12-02
source: "Bite Size Linux" (Julia Evans)
---
# file descriptors and pipes

## file descriptors
- Unix systems use integers to track open files. These integers are called file descriptors.
- `lsof` (list open files) will show you a process's open files
- File descriptors can refer to:
    - files on disk
    - pipes
    - sockets (network connections)
    - terminals (like xterm)
    - devices (your speaker, /dev/null, etc.)
    - lots more: eventfd, inotify, signalfd, epoll, etc.
    > Not everything on Unix is a file, but lots of things are
- When you read or write to a file / pipe / network connection, you do that using a file descriptor.
- Let's see how some simple Python code works under the hood:
    ```python
    f = open("file.txt")
    f.readlines()
    ```
    - Behind the scenes:
- (Almost) every process has 3 standard FDs:
    - stdin: 0
        - "read from stdin" means "read from the file descriptor 0", which could be a pipe or file or terminal
    - stdout: 1
    - stderr: 2

## pipes
- Sometimes you want to send the output of one process to the input of another
- A pipe is a pair of 2 magical file descriptors: stdin (pipe input) and stdout (pipe output)
- Pipes are one way. You can't write to output
- Linux create a buffer for each pipe. If data gets written to the pipe faster than it's read, the buffer will fill up. When the buffer is full, writes to input will block (wait) until the readers read.
- What if your target process dies? Then the pipe will close and input process will be sent SIGPIPE. By default, SIGPIPE terminates your process.
- Named pipes (`mkfifo my_pipe`): this lets two unrelated processes communicate through a pipe.
