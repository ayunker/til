# Existence Check

The most efficient way to check for record existence is via `exists?`.

The following AR query will generate the following SQL:

``` Listing.where(id: 123).exists?

=> SELECT 1 FROM listings where id = 123 LIMIT 1 ```

Note: `exists?` will always make a call to the db, so if the query has already
been executed, `any?` can be faster since just hitting memory.

Ref:
https://semaphoreci.com/blog/2017/03/14/faster-rails-how-to-check-if-a-record-exists.html
