# Scan with Index

If you want to search for a pattern in a string and get back all the matches of that pattern, you can use `String#scan`:

``` ruby
irb(main)> "..123...456...123".scan(/\d+/)
=> ["123", "456", "123"]
```

This is super useful. But sometimes, it would be even more useful to also know the index of where the match starts. Turns out, you can do this with `$~`

``` ruby
irb(main)> matches_with_index = []
irb(main)* "..123...456...123".scan(/\d+/).map do |x|
irb(main)*   [x, $~.offset(0)[0]]
irb(main)> end
irb(main)> matches_with_index
=> [["123", 2], ["456", 8], ["123", 14]]
```

`$~` is a global variable that's equivalent to `Regexp.last_match`, which is the `MatchData` for the last successful pattern match - it basically lets you get some data about the last thing `Regexp` matched. 

`MatchData#offset` returns an array with the starting and ending offsets of the match. So `$~.offset(0)[0]` -> the offset to the start of the match, and `$~.offset(0)[1]` -> the offset to the end of the match.

via https://til.hashrocket.com/posts/35dabq64oa-ruby-scan-with-index
