# ActiveModel Comparison Validator Also Does A Presence Validation

In ActiveModel, a comparison validation on an attribute will first do a presence validation, and return a `:blank` error if the attribute is not present. So you don't have to explicitly add a presence validation if you're also doing a comparison validation (unless you really really want to).

``` ruby
class SomeClass
  include ActiveModel::Model
  include ActiveModel::Attributes

  attribute :some_number

  validates(
    :some_number,
    comparison: {greater_than: 8}
  )
end
```

If you don't provide `some_number`, you'll get a `:blank` error, and the comparison validation will not run:

``` ruby
pry(main)> foo = SomeClass.new
pry(main)> foo.valid?; foo.errors.full_messages
=> ["Some number can't be blank"]
```

But if you do provide `some_number`, then the comparison validation will run as expected:

``` ruby
pry(main)> bar = SomeClass.new(some_number: 3)
pry(main)> bar.valid?; bar.errors.full_messages
=> ["Some number must be greater than 8"]
```

[Source](https://github.com/rails/rails/blob/main/activemodel/lib/active_model/validations/comparison.rb#L24)

via https://til.hashrocket.com/posts/eovmkimoxl-comparison-validator-also-validates-presence
