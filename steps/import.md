---
layout: default
---

### Import data using a sqldump file:

One can use the `mysqldump` utility to export and import data into a database. There is a mysql dump file added to  this repository that you can use as a starting point for your Nelisa's database, it's called `Spaza-MySQL-Dump.sql`.

You can use it like this

Type in the terminal:

```
mysql -u root -p
```

This tells MySQL that you want to log in. `-u root` means the user called root. `-p` means log in with a password. Since we didn't supply a password, MySQL will ask us for one.

Then do:

```
mysql> create database <you db name>;
mysql> use <your db name>;
mysql> source Spaza-MySQL-Dump.sql;
```

You can import the dump file from the terminal using `mysqldump` as well.

After importing the dump file into your database you should have two tables in your database:
* sales_csv
* stock_purchases_csv
