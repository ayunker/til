# Vim Stores the Current Buffers Path in a Register

Registers in (n)vim contain a lot of super useful data. To wit, the `%`
register stores the path of the current buffer. Some useful things we can do
with this register:

* Write the path of the current buffer [into the file
in](https://til.hashrocket.com/posts/be69ff94b2-paste-a-register-from-insert-mode)
`Insert Mode`: `ctrl + R`, `%`
* If in `Normal Mode`: `"%p`
* Copy the path to the clipboard: run the command `"let @+=@%` (copy the `%`
buffer into the `+` buffer, usually used by the system clipboard), or [echo
it](https://til.hashrocket.com/posts/bm2kh55onn-get-the-path-to-the-current-buffer-in-vim)

via https://til.hashrocket.com/posts/yj6jckdc9u-vim-stores-the-current-buffers-path-in-a-register
