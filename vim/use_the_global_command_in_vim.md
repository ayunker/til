# Use the Global Command in Vim

Today I learned about the `global` command in (n)vim, which allows you to run a
command on multiple lines matching a pattern.

Let's say I want to remove all lines in a file matching `pattern1`. In command
mode, I can do this with:

```
:g/pattern1/d_
```

(The vim `:help` file recommends using `d_` to avoid clobbering registers,
which will make it faster)

Any ex command is a valid command, and you can also execute normal mode
commands with `norm`

```
:g/pattern1/norm {command}
```
