# mysql Config File

With `mysql`, I found myself typing a lot of commands specifying the port,
host, user and password, like this. (`-p` is for password, and you'll be
prompted for it):

``` bash
% mysql -h 127.0.0.1 -P 3307 -u iou -p -e "SHOW DATABASES;"
```

Turns out, you can shove all that boilerplate into a config file at `~/.my.cnf`

```ini
[client]
host=127.0.0.1
port=3307
user=username
password=totallysecretpassword
```

The `[client]` section is read by every client program, like `mysql`,
`mysqladmin`, `mysqldump`, etc.

You can put `mysql` (interactive shell) in `[mysql]` section, like:

``` ini
[mysql]
database=iou_development # default DB
prompt=\u@\h:\p [\d]>\_ # shows user@host:port [db]>
auto-rehash # tab-completion of table/column names
pager=less -SFX # wide results scroll sideways instead of wrapping
```

You can also have "profiles" with group suffixes. So if you wanted a staging
profile, you could do:

```ini
[client]
host=127.0.0.1
port=3307
user=username
password=totallysecretpassword

[client_staging]
host=staging-db.real.com
port=3306
user=username
password=totallysecretstagingpassword
```

Then you can use it with:

```bash
mysql --defaults-group-suffix=_staging -e "SHOW DATABASES;"
```

It's kinda gross, but I guess it's something.
