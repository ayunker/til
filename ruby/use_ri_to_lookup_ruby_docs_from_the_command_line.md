# Use ri to Lookup Ruby Docs from the Command Line

Did you know you can look up ruby documentation on Classes and methods from the command line? The slightly elusive `ri` command does just that. You can pass it an argument of the class/method you want to look up, or you can enter interactive mode without arguments.

```
$ ri uniq

$ ri Array#compact

$ ri Hash
```


You can also use it to browse all the pre-defined ruby global variables:

```
$ ri ruby:globals
```

Check out the [docs](https://ruby.github.io/rdoc/RI_rdoc.html) or run `ri --help` to see all it can do.

h/t [Brian Dunn](https://til.hashrocket.com/authors/briandunn)

via https://til.hashrocket.com/posts/qikoqbtcc5-use-ri-to-lookup-ruby-docs-from-the-command-line
