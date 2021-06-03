# Partial Indexes

Postgres supports creating partial indexes on a table, so we can add indexes
(and unique indexes) to a subset of the table.

``` sql
CREATE TABLE users ( email varchar, name varchar, removed_at bool);
```

Given the above table, we can enforce a unique index on email for active users
by

``` sql
CREATE UNIQUE INDEX unique email ON users (email) where (removed_at IS NULL);
```

Ref: https://www.postgresql.org/docs/9.6/indexes-partial.html
