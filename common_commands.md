# PostgreSQL common commands

## 1. Create new users and databases

### Accessing a Postgres Prompt Without Switching Accounts

```shell
$ sudo -u postgres psql
```

You can exit the interactive Postgres session by typing:

```shell
postgres=# \q
```

### Create a New Role

```shell
$ sudo -u postgres createuser --interactive
```

### Create a New Database

```shell
$ sudo -u postgres createdb my_db
```

### Check the Connection Information

```shell
sammy=# \conninfo
```

### References

- [How To Install and Use PostgreSQL on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04)

## 2. Rename a Column of a Table

### Single Column

```shell
ALTER TABLE table_name
RENAME COLUMN column_name TO new_column_name;
```

### Multiple Columns

```shell
ALTER TABLE table_name
RENAME column_name_1 TO new_column_name_1,
RENAME column_name_2 TO new_column_name_2,
...;
```

## 3. Rename a Database

```shell
ALTER DATABASE "old_name" RENAME TO "new_name";
```

## 4. Add New Columns to a table

```shell
ALTER TABLE table_name
ADD COLUMN new_column_name_1 data_type constraint,
ADD COLUMN new_column_name_2 data_type constraint,
...
ADD COLUMN new_column_name_n data_type constraint;
```

## 5. List tables

```shell
\dt
```

or

```shell
SELECT * FROM pg_catalog.pg_tables;
```

## 6. Dump and restore

[PostgreSQL Documentation: `pg_dump`](https://www.postgresql.org/docs/current/app-pgdump.html)

### Dump

```shell
$ sudo -u my_dba pg_dump my_db > my_db_dump.sql
```

### Restore

<!-- Attention: you may need to change the file mode to allow the dba user allowed to read the dumped file `my_db_dump.sql`. If your current user is `derek`, then you can achieve this by:

```
# chgrp my_dba my_db_dump.sql
# usermod -aG my_dba derek
```

Then both `my_dba` and `derek` (who are now both in the `my_dba` group) can read the file `my_db_dump.sql` -->

Create a new database `my_db`:

```shell
$ sudo -iu postgres createdb -O my_dba my_db
```

Script:

```shell
$ sudo -iu my_dba psql -d my_db -f my_db_dump.sql
```
