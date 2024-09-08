# casecmp to Compare Strings

TIL about [`casecmp`](https://ruby-doc.org/3.3.5/String.html#method-i-casecmp)
and `casecmp?` to compare strings in ruby.

`casecmp` compares the downcase of both strings under comparison, and returns
`1` if the compared string is smaller, `-1` if it's larger, and `0` if it's
equal` (and `nil` if they can't be compared).

```ruby
"hashrocket".casecmp("hashrocket") # => 0
"hashrocket".casecmp("hAsHrOcKeT") # => 0
"hashrocket".casecmp("hashrocket123") # => -1
"hashrocket".casecmp("hashrock") # => 1
"hashrocket".casecmp(123) # => nil
```

[`casecmp?`](https://ruby-doc.org/3.3.5/String.html#method-i-casecmp-3F) does
the same comparison but just returns a boolean.

```ruby
"hashrocket".casecmp("hAsHrOcKeT") # => true
"hashrocket".casecmp("hashrock") # => false
"hashrocket".casecmp(123) # => nil
```

h/t [Brian Dunn](https://til.hashrocket.com/authors/briandunn)

via https://til.hashrocket.com/posts/rwbdqxt6fr-casecmp-to-compare-strings
