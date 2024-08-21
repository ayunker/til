# Ruby GraphQL Generators

Today I Learned the [GraphQL ruby gem](https://graphql-ruby.org/) includes
[generators](https://graphql-ruby.org/schema/generators.html#scaffolding-types)
for types, mutations and other fun things.

```
rails g graphql:object
rails g graphql:input
rails g graphql:interface
rails g graphql:union
rails g graphql:enum
rails g graphql:scalar
rails g graphql:mutation
```

What's even neater is if the name of thing things you're generating matches an
existing ActiveRecord model, it will scaffold all the database columns as
fields!

If you have a model `Book` like:
``` ruby
class Book < ApplicationRecord
  attribute :id
  attribute :author_id
  attribute :title
  attribute :published_at
end
```

Running the object generator `rails g graphql:object Book` will produce:

``` ruby
module Types
  class BookType < Types::BaseObject
    field :id, ID
    field :author_id, ID
    field :title, String
    field :published_at, GraphQL::Types::ISO8601DateTime
  end
end
```

via https://til.hashrocket.com/posts/a6vlnujimh-ruby-graphql-generators
