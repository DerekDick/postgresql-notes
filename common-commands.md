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

## References

- [How To Install and Use PostgreSQL on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04)
