# Ruby Rightward Assignment for Javascript-like Destructuring

It's not often there's a javascript feature I wish was available in ruby, but here we are. But, it turns out ruby has the functionality as of 2.7 and I was just out of the loop.

In javascript you can use destructuring assignment to unpack a bunch of variables in a single line:

``` javascript
const obj = { a: 1, b: 2, c: 3, d: 4 }
const { a, b, d: newName } = obj
console.log([a, b, newName])
// => [1, 2, 4]
```

With rightward assignment (available starting in ruby 2.7) you can do a similar thing with hashes, though with slightly different syntax

``` ruby
hsh = { a: 1, b: 2, c: 3, d: 4 }
hsh => { a:, b:, d: new_name }
puts [a, b, new_name]
# => [1,2,4]
```

Nice!

More here: https://docs.ruby-lang.org/en/master/syntax/pattern_matching_rdoc.html#label-Pattern+matching

via https://til.hashrocket.com/posts/8lykl50rsp-ruby-rightward-assignment-js-like-destructuring
