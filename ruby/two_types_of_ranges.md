# Two Types of Ranges

Today I learned there are two ways to construct a
[range](https://ruby-doc.org/3.2.2/Range.html) in ruby. Using two dots `..`
creates a range including the start and end values.
``` ruby
(2..5).include?(2) # => true
(2..5).include?(5) # => true
```

Using three dots `...` creates a range including the start value, but *not* the
end value.
``` ruby
(2...5).include?(2) # => true
(2...5).include?(5) # => false
```

So if we think of them in terms of
[intervals](https://en.wikipedia.org/wiki/Interval_(mathematics)), `(a..b)` is
a closed interval (`[a, b]`), and `(a...b)` is a right half-open interval (`[a,
b)`).

via https://til.hashrocket.com/posts/cjcydjep8n-two-types-of-ranges-in-ruby
