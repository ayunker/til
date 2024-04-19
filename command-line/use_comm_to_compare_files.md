# Use Comm to Compare Files

Today I learned about `comm`, which is used to select the **comm**on lines in
two files. It's pretty neat, but has a strange output format.

Say we have two text files:

```
# first.txt
one
two
three

# second.txt
one
three
four
```

We can run the below command to find the common lines. In the output, the first
column is what's only in `first.txt`, the second column is what's in
`second.txt`, and the third column is what's common.

``` sh
$ comm first.txt second.txt
                one
        three
        four
two
three
```

Hmm, that doesn't look right - `one` **and** `three` are common, not just
`one`. The caveat with `comm` is that the files need to be sorted lexically.
You can sort easily in bash with [bird beak notation for process
substitution](https://til.hashrocket.com/posts/e1a3a9fa24-bird-beak-bash-or-process-substitution).

``` sh
$ comm <(sort first.txt) <(sort second.txt)
        four
                one
                three
two
```

If we only want the common lines, we can apply the flags `-12` to hide the
first and second columns:

``` sh
$ comm -12 <(sort first.txt) <(sort second.txt)
one
three
```

via https://til.hashrocket.com/posts/s7yn6gelbq-use-comm-to-compare-files
