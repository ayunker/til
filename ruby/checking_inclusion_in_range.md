# Checking Inclusion in Range

Let's say you want to check if a number is between 1 and 3 in ruby.

You can use `#include?`:

```ruby 
(1..3).include?(2) 
# => true
(1..3).include?(3) 
# => true
(1..3).include?(5) 
# => false
```

You can also use the [threequals](https://docs.ruby-lang.org/en/3.3/Range.html#method-i-3D-3D-3D) operator `===`:

``` ruby
(1..3) === 2
# => true
(1..3) === 3
# => true
(1..3) === 5
# => false
```

Both methods can be used on [inclusive and exclusive ranges](https://til.hashrocket.com/posts/cjcydjep8n-two-types-of-ranges-in-ruby)

via https://til.hashrocket.com/posts/las2rgviv4-checking-inclusion-in-range-in-ruby
