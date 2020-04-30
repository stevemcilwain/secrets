# rpcclient commands

## common RIDs

* 0x200 (512) - Domain Admins
* 0x201 (513) - Domain Users
* 0x207 (519) - Enterprise Admins
* 0x3e8 (1000) - domain users start here and increment

## netlogon

```
dsr_getdcname
dsr_enumtrustdom
```

## lsarpc

```
lsaquery
lookupsids <SID>
lookupnames <NAME>
```

## samr

```
enumdomains
enumdomusers
queryuser <RID> / <name>
querygroupmem <RID>
getdompwinfo
enumlocalgroups builtin
queryaliasmem builtin 0x220 #local admins group
```
