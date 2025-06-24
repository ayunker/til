# Edit Source Code from Within Pry

Yesterday I learned (YIL?!) how to override instance methods within `pry`. But
what if you like the change and want make it more permanent? Typically what I
would do is edit the appropriate file, and either `reload!` within `pry` or
restart the session. 

I learned you can also edit the code directly from within `pry` - if I want to
edit the `User` class, I can run `edit User` and pry will open the file that
defines `User` in your `$EDITOR` ((n)vim, natch). When you close the file,
you'll be dropped back into your `pry` session and the code will be reloaded
(including any instances of the class you already spun up).

```
class User
  def name = "tony"
end

pry(main)> me = User.new
pry(main)> me.name
# => "tony"

pry(main)> edit User # and let's say we edit name to return 'not-tony'
pry(main)> me.name
# => "not-tony"
pry(main)> User.new.name
# => "not-tony"
```

This feels like a step closer to a LISPer's ideal of a REPL.

via https://til.hashrocket.com/posts/n0glcoitjp-edit-source-code-from-within-pry
