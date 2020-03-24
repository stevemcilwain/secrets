# MSSQL- Metadata

## Get Databases
```
SELECT name FROM master.dbo.sysdatabases
```

## Get tables in DB
```
SELECT * FROM <DB>.INFORMATION_SCHEMA.TABLES
```

## Get columns in a table
```
SELECT * FROM <DB>.INFORMATION_SCHEMA.COLUMNS
```

## use
```
USE <DB>
```