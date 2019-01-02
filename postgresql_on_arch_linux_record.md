# PostgreSQL on Arch Linux

## Installation

```shell
$ sudo pacman -S postgresql
```

## Initial configuration

```shell
$ sudo -u postgres -i
[postgres]$ initdb -D '/var/lib/postgres/data'
```

```shell
$ sudo systemctl start postgresql.service
$ sudo systemctl enable postgresql.service
```

## Create your first database and User

```shell
[postgres]$ createuser --interactive
```

```shell
$ createdb my_db
```

```shell
$ sudo useradd my_dba
```

## Set the password for the user

```shell
$ sudo -u my_dba psql -d my_db
my_db=> ALTER USER my_dba PASSWORD 'mypassword';
my_db=> \q
```
