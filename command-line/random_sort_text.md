# Random Sort Text

You can `sort` to sort text in a file or STDIN. But what if you want to throw
out determinism and sort randomly? Turns out, there's a few ways to do that.

* `sort -R file.txt` - `sort`'s `-R` option does a random sort rather than
lexicographically. The caveat here is if you have duplicates, they will be
grouped together in the resulting output.
* `shuf file.txt` - `shuf` is a standalone utility to generate random
permutations.

Read the [man
pages](https://til.hashrocket.com/posts/xghstaze5p-read-man-pages-in-nvim) to
learn more!

via https://til.hashrocket.com/posts/3qhfvzatis-random-sort-text
