# Ruby's Abbreviated Assignment Operators

Today I Learned ruby has a lot of [abbreviated assignment operators](https://ruby-doc.org/3.2.2/syntax/assignment_rdoc.html#label-Abbreviated+Assignment).

The best known are `+=` and `-=` to increment and decrement values:

```ruby
x = 2
x += 1
x #=> 3
```

And of course there's `||=`, to assign only if the value is `nil` or `false`:

```ruby
x = nil
x ||= 4 #=> 4
x ||= 5 #=> 4
```

But these abbreviations can be applied to a lot more operators! 
It works with all of the following: `+`, `-`, `*`, `/`, `%`, `**`, `&`, `|`, `^`, `<<`, `>>`, `&&`, `||`.

So we could use `|=` to union two arrays and assign the result to the variable:

```ruby
x = [1, 2, 3]
x |= [2, 3, 4, 4]
x #=> [1, 2, 3, 4]
```
