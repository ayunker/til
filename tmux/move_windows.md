# Move Windows

Today I learned you can use the `swap-window` command to move windows in tmux.

If you want to move the current window to the first position (assuming indexed
with 1):
```
:swap-window -t 1
```

Or more generalle:
```
:swap-window -t [index]
```

Or to move relatively to the left or right:
```
:swap-window -t -1
:swap-window -t +1
```

h/t [Dorians TIL](https://til.hashrocket.com/posts/6vz1uo5bxv-move-window-tab-in-tmux)

