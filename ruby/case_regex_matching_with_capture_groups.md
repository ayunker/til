# Case Regex Matching with Capture Groups

I ran into a problem today where I wanted to use a `case` statement to match
against a regex, but also capture a couple of values from the matched data. 

Say I want to match on a pair of numbers wrapped in parens like `(2,4)` and add
them together. If i match without capture groups I have to grab the numbers
again in the `when` block:

``` ruby
x = "(2,4)"
case x
when /\(\d+,\d+\)/
  a,b = x.scan(/\d+/)
  a.to_i + b.to_i
end
# => 6
```

Seems such a shame to have perform another op to get `a` and `b`. What if we
used [capturing
groups](https://ruby-doc.org/3.3.6/Regexp.html#class-Regexp-label-Groups+and+Captures)
like `/\((\d+),\(d+)\)/`? How do we refer to those captured values inside the
`when`? We can use some of ruby's special variables, namely `$1` and `$2` to
refer to the enumerated capture groups of the last regular expression.

``` ruby
x = "(2,4)"
case x
when /\((\d+),(\d+)\)/
  $1.to_i + $2.to_i
end
# => 6
```

`$1` and `$2`  feel a little magic, so we can name our capture groups `group1`
and `group2`, get access those from `$~` (the `MatchData` of the last regular
expression).

``` ruby
x = "(2,4)"
case x
when /\((?<group1>\d+),(?<group2>\d+)\)/
  $~[:group1].to_i + $~[:group2].to_i
end
# => 6
```

via https://til.hashrocket.com/posts/brvfrcnvxu-case-regex-matching-with-capture-groups
