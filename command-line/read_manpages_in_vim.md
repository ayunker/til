# Read Manpages in vim

Reading man pages in (n)vim is my new favorite way to read man pages and a
total gamechanger! (n)vim gives you syntax highlighting, plus you can follow
the links with `Shift + K` (yes, there are links between man pages - I never
knew!).

You can override the default pager for `man` by setting the `MANPAGER`
environment variable (the default is `less -sR`) - per the [nvim help
page](https://neovim.io/doc/user/filetype.html#_man), you can use nvim with
`export MANPAGER='nvim +Man!'`.

Happy manual reading!

h/t [Josh Branchaud](https://til.hashrocket.com/authors/joshbranchaud), the TIL
GOAT.

via https://til.hashrocket.com/posts/xghstaze5p-read-man-pages-in-nvim
