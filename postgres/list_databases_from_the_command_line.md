# List Databases from the Command Line

Today I learned how to list postgres databases from the command line. I use
`createdb` and `dropdb` all the time to create and drop databases, but alas
found out `listdb` is **not** a valid command. 

Instead, you can list the databases with `psql -l`.


```
$ psql -l
             Name             |  Owner   | Encoding |   Collate   |    Ctype    | ICU Locale | Locale Provider |   Access privileges
-----------------------------+----------+----------+-------------+-------------+------------+-----------------+-----------------------
 postgres                    | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | en-US      | icu             |
 template0                   | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | en-US      | icu             | =c/postgres          +
                             |          |          |             |             |            |                 | postgres=CTc/postgres
 template1                   | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | en-US      | icu             | =c/postgres          +
                             |          |          |             |             |            |                 | postgres=CTc/postgres
...
```


[Docs](https://www.postgresql.org/docs/current/app-psql.html#APP-PSQL-OPTION-LIST)
