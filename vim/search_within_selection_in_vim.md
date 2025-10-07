# Search within Selection in Vim

`\%V` is a useful *atom* (TIL it's called an atom - and there are a *lot* of
them, see `:h pattern-atoms`) that can be used to match inside a Visual
selection.

Say you have a large file open and want to search for something only within a
single area of text, like a method. You can visually select that block of text,
enter command mode with `:`, and prefix the search with `\%V` to scope the
search so that you only get matches inside the selection:

```
:'<,'>/\%Vsearch_text
```

You can also use `\%V` to [search and
replace](https://til.hashrocket.com/posts/xymt88n9dk-how-to-restrict-visually-selected-replace).

via https://til.hashrocket.com/posts/lzwrv8ffvd-search-within-selection-in-vim
