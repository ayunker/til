# Delete Lines with Patterns and Ex Commands

Today I learned some cool ways to delete lines of text in (n)vim. [Josh
TIL'ed](https://til.hashrocket.com/posts/11b908779e-delete-lines-that-match-a-pattern)
that you can execute an Ex command on a buffer with the `:g` command. So if you
want to delete any lines that match *pattern*, you can run 

```
:g/pattern/d
```

Which is pretty neat! But you can also flip it - to delete any lines that
**don't** match the pattern, you can use `:v` or `:g!`

```
:v/pattern/d
```

```
:g!/pattern/d
```

You can also restrict to a range of lines - if you want to only delete lines
matching *pattern* between lines 40 and 50, you can do so with:

```
:40,50 g/pattern/d
```

Docs: `:h :g`

via https://til.hashrocket.com/posts/wwyk7usrgq-delete-lines-with-patterns-and-ex-commands
