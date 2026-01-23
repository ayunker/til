# Limit Rows Returned in Oracle SQL

Postgres has a lovely `LIMIT` clause that allows you to limit the number of
returned rows.

```sql
SELECT *
FROM blogs
LIMIT 10;
```

Oracle SQL does not have a `LIMIT` clause (one of the many reasons why FOSS is
better 😉) Instead, it has `FETCH` which will do the same thing, albeit more
verbosely.

```sql
SELECT *
FROM blogs
FETCH FIRST 10 ROWS ONLY;
```

`FETCH` is available in Oracle 12c and above. On older Oracle versions, you can
use the `ROWNUM` pseudo column. Keep in mind it's 1-based indexing.

```sql
SELECT *
FROM blogs
where ROWNUM <= 10
```

via https://til.hashrocket.com/posts/2e7a5urirx-limit-rows-returned-in-oracle-sql
