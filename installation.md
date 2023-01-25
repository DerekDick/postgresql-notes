# Install PostgreSQL

## Ubuntu 16.04

Ubuntu's default repositories contain Postgres packages, so we can install these easily using the `apt` packaging system.

Since this is our first time using `apt` in this session, we need to refresh our local package index. We can then install the Postgres package and a `-contrib` package that adds some additional utilities and functionality:

```shell
$ sudo apt-get update
$ sudo apt-get install postgresql postgresql-contrib
```

### References

- [How To Install and Use PostgreSQL on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04)

## Arch Linux

Please refer to [PostgreSQL - ArchWiki](https://wiki.archlinux.org/index.php/PostgreSQL)

## macOS

Using Homebrew

```shell
$ brew install postgresql
$ brew services start postgresql@10
```
