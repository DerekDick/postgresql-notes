# Create a copy of a database in PostgreSQL

[Reference](https://stackoverflow.com/questions/876522/creating-a-copy-of-a-database-in-postgresql)

```shell
CREATE DATABASE newdb WITH TEMPLATE originaldb OWNER dbuser;
```

If you get:

```shell
ERROR:  source database "originaldb" is being accessed by other users
```

then run:

```shell
SELECT pg_terminate_backend(pg_stat_activity.pid) FROM pg_stat_activity
WHERE pg_stat_activity.datname = 'originaldb' AND pid <> pg_backend_pid();
```
