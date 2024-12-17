# GNU[^01] coreutils

[^01]: ["Overview of the GNU System" (gnu.org)](https://www.gnu.org/gnu/gnu-history.en.html)

- stdin, stdout, stderr[^1].

- redirecting, piping[^1].
  - [https://unixgame.io/unix50](https://unixgame.io/unix50)

- info, man[^2].

[^1]: [file descriptors and pipes](1-file_descriptors_and_pipes.md)
[^2]: [man page sections](2-man_page_sections.md)

## Lines

[read] cat\*, grep, head/tail, tee, (shuf, short, uniq, wc)

\*: more, less

[write] echo/printf, seq, yes. cut, tr, awk, sed, tac

## (plaintext) Files

> # File types[^02]
> Within the file system, each file is marked with a type, indicating what kind of file it is.
> One of these file types denotes ordinary data files, which are usually called regular or plain files to distinguish them from other file types.
> These other file types include devices, pipes, sockets, directories, and symbolic links.
> The term file is commonly used to denote a file of any type, not just a regular file.

> # Directories and links[^02]
> A directory is a special file whose contents take the form of a table of filenames coupled with references to the corresponding files.
> This filename-plus-reference association is called a link, and files may have multiple links, and thus multiple names, in the same or in different directories.
> Directories may contain links both to files and to other directories.
> The links between directories establish the directory hierarchy.
> Every directory contains at least two entries: . (dot), which is a link to the directory itself, and .. (dot-dot), which is a link to its parent directory, the directory above it in the hierarchy.
> Every directory, except the root directory, has a parent.
> For the root directory, the dot-dot entry is a link to the root directory itself (thus, /.. equates to /).

[^02]: ["The Linux Programming Interface", (M. Kerrisk)](https://man7.org/tlpi/)

permissions[^3], encoding, binaries.

> # Programs[^02]
> Programs normally exist in two forms.
> The first form is source code, human-readable text consisting of a series of statements written in a programming language such as C.
> To be executed, source code must be converted to the second form: binary machine-language instructions that the computer can understand.
> (This contrasts with a script, which is a text file containing commands to be directly processed by a program such as a shell or other command interpreter.)
> The two meanings of the term program are normally considered synonymous, since the step of compiling and linking converts source code into semantically equivalent binary machine code.

[^3]: [unix permissions](3-unix_permissions.md)

[read] dir, {colors}, ls, pwd/basename, find, file. cksum, {md5,sha1,sha256}sum. xdd, strings

[write] mkdir, ch{mod,own,..} (cp, mv, rm, ln, link, touch), (vi, ed), (mkfifo, mktemp). dd

## Shell

filesystems, "all is a file", users/groups, processes, signals.

> # Process[^02]
> Put most simply, a process is an instance of an executing program.
> When a program is executed, the kernel loads the code of the program into virtual memory, allocates space for program variables,
> and sets up kernel bookkeeping data structures to record various information (such as process ID, termination status, user IDs, and group IDs) about the process.

> # Shell[^02]
> A shell is a special-purpose program designed to read commands typed by a user and execute appropriate programs in response to those commands.
> Such a program is sometimes known as a command interpreter.
> Whereas on some operating systems the command interpreter is an integral part of the kernel, on UNIX systems, the shell is a user process.
> The shells are designed not merely for interactive use, but also for the interpretation of shell scripts, which are text files containing shell commands.
> For this purpose, each of the shells has the facilities typically associated with programming languages: variables, loop and conditional statements, I/O commands, and functions.

> # Signal[^02]

> # Process termination and termination status[^02]
> A process can terminate in one of two ways: by requesting its own termination using the `_exit()` system call (or the related `exit()` library function), or by being killed by the delivery of a signal.
> In either case, the process yields a termination status, a small nonnegative integer value that is available for inspection by the parent process using the `wait()` system call.
> In the case of a call to `_exit(),` the process explicitly specifies its own termination status.
> If a process is killed by a signal, the termination status is set according to the type of signal that caused the death of the process.
> (Sometimes, we’ll refer to the argument passed to `_exit()` as the exit status of the process, as distinct from the termination status, which is either the value passed to `_exit()` or an indication of the signal that killed the process.)
> By convention, a termination status of 0 indicates that the process succeeded, and a nonzero status indicates that some error occurred.
> Most shells make the termination status of the last executed program available via a shell variable named `$?`.

> # Process user and group identifiers (credentials)[^02]

> # Privileged processes

[read] df, du. date, host{id,name}, uptime, (nproc, uname). groups, users, whoami. printenv
 ps, lsof, netstat, top, mem, ...

[write] sleep, nice, kill, nohup, timeout. env, wall. su, sudo, who. paralell. tar

## Network

ip, ifconfig, route
curl, dig, ssh, nmap, telnet, nc, ping, traceroute, tcpdump

## {yester,to}day

bat. tree. screen, tmux, asciinema. htop. watch, viddy. column, jq, csvkit, csvlens
