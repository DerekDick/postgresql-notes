# Create User and Database on PostgreSQL

## Accessing a Postgres Prompt Without Switching Accounts

```shell
$ sudo -u postgres psql
```

You can exit the interactive Postgres session by typing:

```shell
postgres=# \q
```

## Create a New Role

```shell
$ sudo -u postgres createuser --interactive
```

## Create a New Database

```shell
$ sudo -u postgres createdb my_db
```

## Check the Connection Information

```shell
sammy=# \conninfo
```

## References

- [How To Install and Use PostgreSQL on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04)

# Rename a Column of a Table

## Single Column

```shell
ALTER TABLE table_name 
RENAME COLUMN column_name TO new_column_name;
```

## Multiple Columns

```shell
ALTER TABLE table_name
RENAME column_name_1 TO new_column_name_1,
RENAME column_name_2 TO new_column_name_2,
...;
```
