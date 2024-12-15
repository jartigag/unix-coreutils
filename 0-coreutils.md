# GNU[^0] coreutils

[^0]: [https://www.gnu.org/gnu/gnu-history.en.html](https://www.gnu.org/gnu/gnu-history.en.html)

- [x][^1] stdin, stdout, stderr.

- [x][^1] redirecting, piping.
  - [https://unixgame.io/unix50](https://unixgame.io/unix50)

- [x][^2] info, man.

[^1]: [file descriptors and pipes](1-file_descriptors_and_pipes.md)
[^2]: [man page sections](2-man_page_sections.md)

## Lines

[read] cat*, grep, head/tail, tee, (shuf, short, uniq, wc)

*: more, less

[write] echo/printf, seq, yes. cut, tr, awk, sed, tac

## (plaintext) Files

permissions[^3], encoding, binaries.

[^3]: [unix permissions](3-unix_permissions.md)

[read] dir, {colors}, ls, pwd/basename, find, file. cksum, {md5,sha1,sha256}sum. xdd, strings

[write] mkdir, ch{mod,own,..} (cp, mv, rm, ln, link, touch), (vi, ed), (mkfifo, mktemp). dd

## Shell

filesystems, "all is a file", users/groups, processes, signals.

[read] df, du. date, host{id,name}, uptime, (nproc, uname). groups, users, whoami. printenv
 ps, lsof, netstat, top, mem, ...

[write] sleep, nice, kill, nohup, timeout. env, wall. su, sudo, who. paralell. tar

## Network

ip, ifconfig, route
curl, dig, ssh, nmap, telnet, nc, ping, traceroute, tcpdump

## {yester,to}day

bat. tree. screen, tmux, asciinema. htop. watch, viddy. column, jq, csvkit, csvlens
