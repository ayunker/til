# Autosave belongs_to Associations

By default, if you make a change to a `belongs_to` associated model and save
the parent model, the associated model won't be saved. This is probably a good
default, but it is overridable with the `:autosave` option.

``` ruby
class Book < ApplicationRecord
  belongs_to :author
end

book = Book.first
book.author.name # => "J.R.R. Tolkein"

book.author.name = "John Tolkein"

book.save
book.reload
book.author.name # => "J.R.R. Tolkein"
```

But we can change this behaviour by setting `:autosave` to true.

``` ruby
class Book < ApplicationRecord
  belongs_to :author, autosave: :true
end

book = Book.first
book.author.name # => "J.R.R. Tolkein"

book.author.name = "John Tolkein"

book.save
book.reload
book.author.name # => "John Tolkein"
```

While this is off by default for `belongs_to` associations, `has_one` and 
`has_many` associations have `:autosave` true because the foreign keys are on 
the associated records to ensure those FKs are kept up to date.

via https://til.hashrocket.com/posts/alkrmpueny-autosave-belongsto-associations
