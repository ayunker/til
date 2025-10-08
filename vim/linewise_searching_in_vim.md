# Linewise Searching in Vim

Today I learned about the `\%l` atom, which can be used to match on the current
line, or a specific line, and also above or below the current or specific line.
That's kind of a lot in one sentence, so lets break it down:

Say you want to search for a `search_term` on line 23 of your buffer, you can
do this with

```
/\%23lsearch_term
```

If you want to search for `search_term` on the current line, you can use `.`

```
/\%.lsearch_term
```

You can use the `<`and `>` modifiers to match above (`<`) or below (`>`) the
current line

```
/\%<.lsearch_term

/\%>.lsearch_term
```

But you can also replace `.` with a line number to match above or below that
line:

```
/\%<23lsearch_term

/\%>23lsearch_term
```

via: https://til.hashrocket.com/posts/auygkgdsn3-linewise-searching-in-vim
