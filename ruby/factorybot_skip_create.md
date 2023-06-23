# FactoryBot skip_create

Factory bot has an option to skip calling `save!` on create:

```ruby
FactoryBot.define do
  factory :model_without_table do
    skip_create
    an_attribute { "An Attribute" }
  end
end
```

This can be useful if you want to create a factory for a model that isn't backed by a database table, where trying to persist the record would result in an exception.

[Docs](https://github.com/thoughtbot/factory_bot/blob/main/GETTING_STARTED.md#custom-methods-to-persist-objects)

via https://til.hashrocket.com/posts/q7eprqi4id-factorybot-skipcreate
