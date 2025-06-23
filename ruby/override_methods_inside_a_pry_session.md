# Override Methods inside a Pry Session

Today I learned you can override methods on an object from within `pry`! Super
helpful if you want to test something out but not change it in code yet.
Important to note this strategy only overrides at the instance level, not the
class level, so other instances won't be affected.

``` ruby
class User
  def name = "tony"
end

pry(main)> me = User.new
pry(main)> me.name
# => "tony"
pry(main)> def me.name = "who, now?"
pry(main)> me.name
# => "who, now?"
pry(main)> other_me = User.new
pry(main)> other_me.name
# => "tony"
```

via https://til.hashrocket.com/posts/mti2yc6fap-override-methods-in-a-pry-session
