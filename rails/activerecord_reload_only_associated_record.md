# ActiveRecord Reload only Associated Record

Today I learned about some focused `reload` methods for ActiveRecord Associations.

Let's say I have an `Author` class that can have one magnum opus.

```ruby
class Author < ApplicationRecord
  has_one :magnum_opus
end
```

Now suppose I've instantiated an `Author`, and his magnum opus gets updated elsewhere. If I try to access that instance's magnum opus again (same instance, no reloading), I'll get the old cached version:

```ruby
author = Author.first
author.magnum_opus.title # => "The Dark Tower"

#elsewhere
mo = MagnumOpus.find_by(title: "The Dark Tower")
mo.update title: "The Shining"

author.magnum_opus.title # => "The Dark Tower"
```

Now to remedy this, we can reload the author:

```ruby
author.reload.magnum_opus.title # => "The Shining"
```

But why reload the whole author when you can reload just the association? ActiveRecord has `reload_*` methods for each `has_one` and `belongs_to` association that does just that - it reloads only the associated record.

```ruby
author.reload_magnum_opus.title # => "The Shining"
```

*(jk his magnum opus is definitely The Dark Tower)*

Docs for [has_one](https://guides.rubyonrails.org/association_basics.html#has-one-association-reference) and [belongs_to](https://guides.rubyonrails.org/association_basics.html#belongs-to-association-reference).

h/t [Matt Polito](https://til.hashrocket.com/authors/mattpolito)

via https://til.hashrocket.com/posts/fh6spyb15g-activerecord-reload-only-associated-record
