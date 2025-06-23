# Use norm Command for Repetitive Text Tasks

Vim macros are great, but they can become tedious if you need to repeat the
macro over and over again on multiple lines. `norm` comes in super handy in
these cases! You can use it to [operate on every
line](https://til.hashrocket.com/posts/619fdc96ed-running-same-vim-command-into-multiple-lines),
or you can apply it to a visual select range.

```
* one,
* two,
* three,
* four,
```

Given a file like above and I want to change just the lines with text `two`,
`three`, by replacing the `*` with a `-` and change the ending comma to a
semicolon, I can visual select those lines (`Shift + V`), enter command mode
with `:` and run:

```
:'<,'>norm 0s-^[$s;
```

Let's break it down:
* `'<,'>` is the visual selection range
* `norm` is the `norm` command
* `0s-` replaces the first character of the line with `-`
* `^[` is actually not typed directly but is an escaped `ESC` char inserted by
`Ctrl + V, Esc`. This allows you to re-enter command mode inside norm mode.
* `$s'` replaces the last character of the line with `;`

After running the command, the file should look like:

```
* one,
- two;
- three;
* four,
```

via https://til.hashrocket.com/posts/lviqdtpcu0-use-the-norm-command-for-repetitive-text-tasks
