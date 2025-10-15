# Check Which Shell You're Using

Sometimes you need to know which shell you're running. It's not a great mystery
most of the time, but sometimes you `ssh` into a new server or spin up a new
distro and it's anybody's guess.

You can check `$0`, which is the path of the currently running program, i.e.
your shell.

``` shell
$ echo $0
-bash
```
