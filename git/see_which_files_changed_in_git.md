# See Which Files Changed in git

`git log` is great to see a detailed diff, but what if you only want to see the files that were changed? 

There's `git whatchanged`, but it's essentially deprecated, and git docs recommend using `git log` instead:

```
% git whatchanged
commit 9925b8ec8fc8024544a36c71e210a23192a63bf4 (HEAD -> main, origin/main, origin/HEAD)
Author: Tony Yunker <tony.yunker@gmail.com>
Date:   Fri Oct 20 15:07:09 2023 -0500

    ruby - abbreviated assignment operators

:100644 100644 7d41153 7449733 M    README.md
:000000 100644 0000000 5a432d1 A    ruby/rubys_abbreviated_assignment_operators.md

```

So then we can use `git log --name-only` to see the names of the files that were changed.

```
% git log --name-only
commit 9925b8ec8fc8024544a36c71e210a23192a63bf4 (HEAD -> main, origin/main, origin/HEAD)
Author: Tony Yunker <tony.yunker@gmail.com>
Date:   Fri Oct 20 15:07:09 2023 -0500

    ruby - abbreviated assignment operators

README.md
ruby/rubys_abbreviated_assignment_operators.md
```

But that won't tell us if they were updates or adds or whatnot. For that, we can use `git log --name-status`

```
% git log --name-status
commit 9925b8ec8fc8024544a36c71e210a23192a63bf4 (HEAD -> main, origin/main, origin/HEAD)
Author: Tony Yunker <tony.yunker@gmail.com>
Date:   Fri Oct 20 15:07:09 2023 -0500

    ruby - abbreviated assignment operators

M   README.md
A   ruby/rubys_abbreviated_assignment_operators.md
```

These flags can be used on `git show` too!

via https://til.hashrocket.com/posts/6mqfnozpql-see-which-files-changed-in-git
