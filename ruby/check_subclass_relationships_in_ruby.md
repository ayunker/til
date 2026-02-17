# Check Subclass Relationships in Ruby

Today I learned the `<` operator can be used to compare classes and their
relationships in their ancestry.

Let's say I have the following class setup:

```ruby
class A end

class B < A
end

class C end
```

Then I can use `<` to determine if `A` is a subclass or ancestor of `B`, and
also see that `B` is not related to `C`:

``` ruby
pry(main)> B < A
# => true


pry(main)> A < B
# => false

pry(main)> B < C
# => nil # no relation
```

There's also `>` which checks the inverse:

``` ruby
pry(main)> B > A
# => false


pry(main)> A > B
# => true

pry(main)> B > C
# => nil # no relation
```

[Docs](https://docs.ruby-lang.org/en/master/Module.html#method-i-3C)

via https://til.hashrocket.com/posts/tu0egszz43-check-subclass-relationships-in-ruby
