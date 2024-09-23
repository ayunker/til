# String Replace in Javascript

I'm very used to  ruby's `gsub(pattern, replacement)`  that does a [g]lobal
[sub]stitution on a string - that is, it replaces all occurrences of the
pattern in the string. If you wanted to just replace the first occurrence of
the pattern you could use `sub`, but I so rarely need to do that I forgot it
existed.

Javascript's equivalent, `replace`, handles things a little bit differently. So
much so I was surprised by it's behavior.

```js
replace(pattern, replacement)
```

`pattern` can be a `string` or a `RegExp`, but you get different replacement
behavior depending on which you use.
* If `pattern` is a string, *only* the first occurrence of `pattern` will be
  replaced.
* If `pattern` is a `RegExp`, by default it will replace the first occurrence,
  unless you pass the global flag to the pattern. So if I wanted to replace
  `asdf` in with `hjkl` in a string, `replace(/asdf/, "hjkl")` will replace
  just the first occurrence. To replace all occurrences, it needs to be
  `replace(/adsf/g, "hjkl)` (note the global `g` flag). 

So maybe the moral of the story is to [always use a
regex](https://xkcd.com/208/) (and remember your flags!).

Docs: [String.prototype.replace\(\) - JavaScript |
MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)

via https://til.hashrocket.com/posts/glfdinm5tk-string-replace-in-javascript
