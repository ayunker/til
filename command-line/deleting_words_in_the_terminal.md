# Deleting Words in the Terminal

I stumbled upon this earlier today, if you're in a terminal and have typed some
things in, pressing `Esc`, then `Backspace` will delete the word on or before
your cursor. `Ctrl` + `W` will do the same thing. 

So if I start typing things in my terminal and want to delete the last word,
like this

``` sh
$ one two three four 
                    ^ cursor here
```

Then `Esc`, `Backspace` will produce

``` sh
$ one two three
               ^ cursor here
```

---

It deletes through the beginning of the word, but starts where the cursor is,
so you can delete partial if your cursor is in the middle of a word

``` sh
$ longer command words
            ^ cursor here
```

Then `Esc`, `Backspace` will produce

``` sh
$ longer and words
         ^ cursor here
```

Confirmed both work in recent versions of `bash` and `zsh`.

via [Today I Learned](https://til.hashrocket.com/posts/x3jbduw0yt-deleting-words-in-the-terminal)
