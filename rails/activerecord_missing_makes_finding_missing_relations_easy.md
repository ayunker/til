# ActiveRecord .missing Makes Finding Missing Relations Easy

It can be kind of clunky to query ActiveRecord for records where the
`has_many`association is empty.

Say I have an `Author` class that has many `Books`. One way to query for
Authors without books is the following:

```ruby
class Author < ApplicationRecord
  has_many :books
end

Author.left_joins(:books).where(books: {id: nil}) 
```

This totally works, but at least for me is difficult to reason what we're
querying. However, Rails 6.1 added a `.missing` method that really helps
clarify what the query is doing:

```ruby
Author.where.missing(:books)
```

Much clearer - this will grab all authors that do not have any books.

[Docs](https://api.rubyonrails.org/classes/ActiveRecord/QueryMethods/WhereChain.html#method-i-missing)
for further reading. Happy querying!

via https://til.hashrocket.com/posts/958vxrt1d3-find-missing-relations-easily-with-missing
