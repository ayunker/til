# List Installed Fonts

Today I learned there's a command line utility called `fc-list`. It lists the
fonts installed on your system. Running `fc-list` will print out a lot of
information - font families, the different styles available, where they're
installed. 

I find it's much more useful to run `fc-list : family`, which will print out all
the font family names installed:

``` sh
$ fc-list : family

Fira Code,Fira Code SemiBold
0xProto Nerd Font
Iosevka Term,Iosevka Term Extrabold
Menlo
.SF NS Mono
...
```

This is a lot easier to read and grep through! 

My main use case for this is if I want to use a font in my
[alacritty](https://alacritty.org/) config, but don't know its name. For
example, if I want to use Apple's new-ish SF Mono font, the font family is not
`SF Mono` - its clearly `.SF NS Mono` 🤷. 

via https://til.hashrocket.com/posts/r66yppihwn-list-installed-fonts-via-the-command-line
