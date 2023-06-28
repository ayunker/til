# Partial Match on Mutliple Columns

If you want to do a partial match on multiple fields on an AR Model, you can do
something like this with `to_tsquery`.

``` ruby
scope :with_name, ->(query) do
  ts_queries = query.split(" ").map do |part|
    "to_tsquery('simple', '#{part}:*')"
  end.join(" && ")

  where(%((first_name || ' ' || last_name) @@(#{ts_queries})))
end
```
