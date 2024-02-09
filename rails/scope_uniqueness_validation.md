# Scope Uniqueness Validation

Let's say you have a blog, with `Authors` and `BlogPosts`. A `BlogPost` has an
`Author` and a title. If we have a requirement that the post titles need to be
unique, our model would look something like this:

``` ruby
class Blog < ApplicationRecord
  has_one :author

  validates :title, uniqueness: true
end
```

Let's say the requirement changes, and the post title needs to be unique to the
author (it's convoluted, but let's roll with it). So Ann can author a post
titled 'Cool Post', and Bob can also author 'Cool Post', but Ann can't publish
another post titled 'Cool Post'. 

Conveniently, uniqueness validations can be scoped to a particular attributes.
So to satisfy the above, we can update the validation to:

``` ruby
class Blog < ApplicationRecord
  has_one :author

  validates :title, uniqueness: {scope: :author_id}
end
```

Refs:
https://boringrails.com/tips/rails-unique-scope

via https://til.hashrocket.com/posts/z9fcynvv69-scoped-uniqueness-validation
