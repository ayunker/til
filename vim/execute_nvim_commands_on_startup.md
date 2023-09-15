# Execute (n)vim Commands on Startup

Today I Learned you can have (n)vim execute a command on startup. 

For example - I often open vim and immediately run `:Git` to open vim-fugitive so I can easily navigate my modified and staged files. But that's 2 steps - 1 more than I want. 

To achieve this, I can run `nvim -c ":Git"`, where the `-c` is the command you want to execute on startup. For even fewer keystrokes you could create an alias!
