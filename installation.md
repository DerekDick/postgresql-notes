# Install PostgreSQL on Ubuntu 16.04

## Commands

Ubuntu's default repositories contain Postgres packages, so we can install these easily using the `apt` packaging system.

Since this is our first time using `apt` in this session, we need to refresh our local package index. We can then install the Postgres package and a `-contrib` package that adds some additional utilities and functionality:

```shell
$ sudo apt-get update
$ sudo apt-get install postgresql postgresql-contrib
```

## References

- [How To Install and Use PostgreSQL on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04)
