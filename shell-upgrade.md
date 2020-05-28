# Fixing Remote Shells

## Upgrade Shell to TTY

```bash
/bin/sh -i
/usr/bin/expect sh
perl: exec "/bin/sh";
lua: os.execute('/bin/sh')
vi> :!bash
vi> :set shell=/bin/bash:shell
nmap> !sh
<sh.exp>
#!/usr/bin/expect
spawn sh
interact
```

## In remote shell

```bash
$ python -c 'import pty; pty.spawn("/bin/bash")'
$ ctrl-z
```

## In local shell

```bash
stty raw -echo
fg
```

## In remote shell

```bash
$ reset
$ export SHELL=bash
$ export TERM=xterm-256color
$ stty rows <num> columns <cols>
```

```bash
$ export SHELL=bash
$ export TERM=xterm256-color
$ stty rows 38 columns 116
$ stty intr ^j
```
