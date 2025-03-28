# Git Commit Reuse Message

Today I learned about the `-C` flag for `git commit`. It's used in Hashrocket's
[dotmatrix](https://github.com/hashrocket/dotmatrix/blob/master/.gitconfig#L6)
in our `git cheddar` alias - `git commit --amend -CHEAD`, but I never actually
dug into what it does.

From the manual: 
> -C <commit>, --reuse-message=<commit>
>
> Take an existing commit object, and reuse the log message and the authorship
> information (including the timestamp) when creating the commit.

Also of note, `-C` doesn't open your editor to edit the message, so it's great
if you don't need to edit the existing message (if you do want to edit,
lowercase `-c` will open your editor with the existing message).

`-CHEAD`....ohhhh that's why it's called `cheddar` 🤯

via https://til.hashrocket.com/posts/eledgmaqib-git-commit-c
