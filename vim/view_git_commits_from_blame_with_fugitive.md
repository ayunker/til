# View Git Commits from Blame with Fugitive

I use [vim-fugitive](https://github.com/tpope/vim-fugitive) all the time to run
a blame on the file I have open in (neo)vim. In the blame buffer, I typically
hit `enter` on a commit to view the full commit in the buffer. It's nice, but
then I need to jump back to view the code again.

Today I learned if you hit `o` instead of `enter`, the commit will open in a
split below, which is much more convenient for me - it allows me to see the
current version of the file, the blame, and the commit in one view. Game
changer.

via: https://til.hashrocket.com/posts/gfbmebcuoi-view-git-commits-from-blame-with-fugitive
