# ActiveRecord List All Enums

Today I learned a way to view all the enums defined on an ActiveRecord Model

Suppose I have a class `Post` with enums `status` and `category`:

``` ruby
class Post < ApplicationRecord
  enum status: [:draft, :published]
  enum category: [:ruby, :rails, :lord_of_the_rings]
end
```

I can view the enum values for statuses with `Post.statuses` and category with
`Post.categories`, but what if I want to see all the enums on `Post`?
`defined_enums` will do that:

```ruby 
Post.defined_enums
=> {
  "status"=>{"draft"=>0, "published"=>1}, 
  "category"=>{"ruby"=>0, "rails"=>1, "lord_of_the_rings"=>2}
}

```

You can of course key in to each enum here too:

``` ruby
Post.defined_enums["status"]
# => {"draft"=>0, "published"=>1}
```
