# From Installation to Usage of PostgreSQL

## Install PostgreSQL on Ubuntu 16.04

```shell
$ sudo apt-get update
$ sudo apt-get install postgresql postgresql-contrib
```

## Create a New Role

```shell
$ sudo -u postgres createuser --interactive
```

## Create a New Database

```shell
$ sudo -u postgres createdb my_db
```

## Add the Created User

```shell
$ sudo adduser my_dba
```

## Set the Password for the Role

```shell
$ sudo -u my_dba psql -d my_db
my_db=# ALTER USER my_dba PASSWORD 'new_password';
```

## Enable Remote Access

### Edit the Configuration File

```shell
$ vim /etc/postgresql/{version}/main/postgresql.conf
...
listen_address='*'
...
```

### Restart PostgreSQL for the Configuration File to Take Effect

```shell
$ invoke-rc.d postgresql restart
```

### Enable Password Authentication Method for the Role

```shell
$ vim /etc/postgresql/9.5/main/pg_hba.conf
host all all all password
```

## Create the Tables

```shell
$ psql -h localhost -U fanscount_dba -d fanscount_db -f create_tables.sql
```
