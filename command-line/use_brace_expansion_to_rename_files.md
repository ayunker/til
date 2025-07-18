# Use Brace Expansion to Rename Files

Today I Learned you can use [brace
expansion](https://www.gnu.org/software/bash/manual/html_node/Brace-Expansion.html)
to rename files in the command line (it works in both bash and zsh).

Brace expansion allows you to generate strings sharing a common prefix or
suffix - perfect for moving/renaming files:

To copy `someFile.js` to `someFile.ts`, you can run:

``` sh
$ cp someFile.{js,ts}
# expands to:
$ cp someFile.js someFile.ts
```

To rename `app/model/blog_test.rb` to `app/model/blog_spec.rb`:

```sh
$ mv app/model/blog_{test,spec}.rb
# expands to:
mv app/model/blog_test.rb app/model/blog_spec.rb
```

via https://til.hashrocket.com/posts/yapr1sarwx-use-brace-expansion-to-rename-files
