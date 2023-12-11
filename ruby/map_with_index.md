# Map with Index

Ever wanted `map_with_index`, like `each_with_index` except for `map` instead of `each`? Turns out you can, with just a 1 character change. `with_index` is a method on `Enumerator` that lets you do just that:

``` ruby
['a', 'b', 'c'].map.with_index do |x, index|
  [x, index]
end
#=> [["a", 0], ["b", 1], ["c", 2]]
```

[Docs](https://ruby-doc.org/3.2.2/Enumerator.html#method-i-with_index)

via https://til.hashrocket.com/posts/qtpg8pcrbq-map-with-index
