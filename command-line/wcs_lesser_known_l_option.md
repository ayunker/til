# wc's Lesser Known -L Option

`wc` is well known for giving you [word, line and character
counts](https://til.hashrocket.com/posts/dh3cotiqxj-the-word-count-command-) of
a file or standard input.

Today I Learned `wc` can also tell you the length of the longest line in a file
with the `-L` flag! 

```
$ cat file.txt
    one
    two
    three

$ wc -L file.txt
    5 file.txt
```

The man pages are full of useful information and trivia. Did you know `wc` has
been around since Unix Version 1?

via [Today I Learned](https://til.hashrocket.com/posts/3sotyaxcmo-wcs-lesser-known-l-option)
