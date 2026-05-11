# Use .first! and .last! ActiveRecord Finder Methods

TIL there are accompanying `!` methods for `.first` and `.last` finder methods.

As you might expect, these methods raise an `ActiveRecord::RecordNotFound` if
there is no first or last record to be found.

[Docs](https://api.rubyonrails.org/classes/ActiveRecord/FinderMethods.html#method-i-first-21)

h/t [Craig Hafer](https://til.hashrocket.com/authors/craighafer)

via https://til.hashrocket.com/posts/hdfgdd8lwc-use-first-and-last-activerecord-finder-methods
