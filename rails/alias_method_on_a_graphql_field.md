# Alias Method on a GraphQL Field

A lot of times I find I have to alias a method on a model when I'm exposing it
on a GraphQL type. Most often I have to do this with `?` methods:

``` ruby
class Post < ApplicationRecord
  def draft?
    ...
  end
end

class PostType < GraphQL::Schema::Object
  field :draft, Boolean, null: false

  def draft
    @object.draft?
  end
end
```

I want the field to be `draft` (without the `?`), but on it's own the GraphQL
ruby gem can't resolve it to `draft?`, so I have to add an additional
definition in the Type class. This works, but it feels clunky.

Turns out you can use the `method:` option on the field to alias the method
inline, which I think streamlines things a good deal:

```ruby
class PostType < GraphQL::Schema::Object
  field :draft, Boolean, null: false, method: :draft?
end
```

[Docs](https://graphql-ruby.org/fields/introduction.html#field-resolution)

via https://til.hashrocket.com/posts/6xs0kvn3nk-alias-method-on-a-graphql-field
