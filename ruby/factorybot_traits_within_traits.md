# FactoryBot Traits within Traits

Today I learned you can nest FactoryBot traits within other traits. Traitception?!

Say you have a blog post model with a `deleted_at` attribute, and an optional `deleted_by` attribute. You could have:

``` ruby
FactoryBot.define do
  factory :post do
    trait :deleted do
      deleted_at { Time.current }
    end

    trait :deleted_by_admin do
      deleted
      deleted_by { :admin }
    end
  end
end
```

There the `deleted` in `deleted_by_admin` references the `deleted` trait above it.

You could alternatively define a new factory that composes the two traits, but it's always nice to have options.
``` ruby
factory :admin_deleted_post, traits: [:deleted, :deleted_by_admin]
```

via https://til.hashrocket.com/posts/qpmhyvxhvg-factorybot-traits-inside-traits
