# Active Record Querying with `and`

ActiveRecord has an `and` method for querying. It does what you think it would do:

```
Post.where(id: [1, 2]).and(Post.where(id: [2, 3]))
# SELECT "posts".* FROM "posts" WHERE "posts"."id" IN (1, 2) AND "posts"."id" IN (2, 3)
```

It's much more common to write the above by chaining `where`s: 

```
Post.where(id: [1, 2]).where(id: [2, 3])
```

However, `and` really shines if you have some more complicated nesting of `AND`s and `OR`s. Say you have a query like this (it's nonsensical, but what we care about is the structure):

```
SELECT "posts".* 
FROM "posts" 
WHERE "posts"."id" IN (1, 2) 
  AND ("posts"."title" = 'title'
    OR "posts"."body" IS NOT NULL)
```

How would you write this in ActiveRecord? If you tried just using `where` and `or`, the nesting of the `or` within the `and` is lost. 

```
Post.where(id: [1,2])
  .where(title: 'title')
  .or(Post.where.not(body: nil))


# SELECT "posts".* 
# FROM "posts" 
# WHERE ("posts"."id" IN (1, 2) 
# 	AND "posts"."title" = 'title' 
# 	OR "posts"."body" IS NOT NULL)
```

Instead of ` A AND (B OR C)` we get `A AND B OR C`, which will not get us what we want. We can use a well-placed `and` to get the right grouping of conditions:

```
Post.where(id: [1,2])
  .and(Post.where(title: 'title')
    .or(Post.where.not(body: nil)))


# SELECT "posts".*
# FROM "posts"
# WHERE "posts"."id" IN (1, 2)
#   AND ("posts"."title" = 'title'
#     OR "posts"."body" IS NOT NULL)
```

[Docs](https://api.rubyonrails.org/v7.0.6/classes/ActiveRecord/QueryMethods.html#method-i-and)

h/t [Craig Hafer](https://til.hashrocket.com/authors/craighafer)

via https://til.hashrocket.com/posts/ocgwhb6uiq-activerecord-query-with-and
