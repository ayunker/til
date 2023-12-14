# End of Line Substitutions

Today I learned a couple of nice regexes for substitutions in (n)vim.

Say you have a list, and you want to replace the character at the end of each line with something else:

```
123@
456@
789!
```

To replace the `@`s and `!` with commas (`,`), you can use this substitute command `:%s/.$/,/`

```
123,
456,
789,
```

The regex `.$` matches the character (`.`) that's at the end of the line (`$`)

Additionally, if you want to add something to the end of each line (but not replace), you can use the substitution `:%s/$/,/` to transform

```
123
456
789
```

into

```
123,
456,
789,
```

via https://til.hashrocket.com/posts/rl42uwodoh-end-of-line-substitutions-in-vim
