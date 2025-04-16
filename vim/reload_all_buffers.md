# Reload All Buffers

In vim `:e` edits the current file, which is useful if the file has been changed outside of vim and you want to load those changes into your buffer in vim.

I ran into a scenario where I ran a formatter outside of vim, and wanted to reload _all_ files open in buffers in my vim session. I took a guess that `:ea` would **e**dit **a**ll (like `:wa` writes all, `:qa` quits all) - but swing and a miss.

The way to do this is with `:bufdo e`. `bufdo` executes the command - in this case `e` - in each buffer in the buffer list.

via https://til.hashrocket.com/posts/mqhcxuijei-reload-all-buffers-in-vim
