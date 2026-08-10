# Use .many? to Determine if Collection has > 1 Records

Today I learned about `many?`, which is a convenience method in ActiveSupport
for determining if there is more than one record present. It's similar to
`any?`, but the key difference is `many?` is strictly greater than, whereas
`any?` is greater than or equal to.

* `any?` returns true if >= 1 record
* `many?` returns true if > 1 record.

`many?` is available on `ActiveRecord::Relation` and `Enumerable` (via
ActiveSupport). When used on `Enumerable` it can be passed a block (similar to
`any?`).

```ruby
people.many? { |p| p.age > 26 }
```

[Docs](https://api.rubyonrails.org/classes/Enumerable.html#method-i-many-3F)

via https://til.hashrocket.com/posts/g5cbkir58d-use-many-to-determine-if-collection-has-1-recs
