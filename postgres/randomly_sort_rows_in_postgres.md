# Randomly Sort Rows in Postgres

I'm on a bit of a random kick lately. Today I learned you can randomly sort
rows returned in a query using Postgres' `random()` function.

``` sql
SELECT *
FROM users
ORDER BY random()
```

What it does is it calculates a random value for each row returned, and then
orders by that calculated value. If the query returns a lot of rows this can be
slow, so probably more useful for exploration or one-offs not necessarily for
production uses.

via https://til.hashrocket.com/posts/wiqsaoudum-randomly-sort-rows-in-postgres
