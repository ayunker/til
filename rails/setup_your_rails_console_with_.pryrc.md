# Setup Your Rails Console with .pryrc

Sometimes there are variables I want to initialize or setup I want to run each
time I enter a rails console, and I don't want to have to type it out every
time. I'm using `pry-rails`, so my rails console is a `pry` session, and I can
add ruby code to my `.pryrc` file to be run on console startup. Conveniently,
this runs after the environment is loaded, so I have access to all my
ActiveRecord models.

``` ruby
# .pryrc
author = Author.find(1)
```

If I put the above in my `.pryrc` file, then I've got `author` available to me
whenever I'm in a rails console (but not when I drop into a pry session in
`rails server` (which is fine, I think it's less useful there)).

You can use a local `.pryrc` in your project's directory, or a global config in
`~/.pryrc`. 

via https://til.hashrocket.com/posts/ghlplm9wpf-setup-your-rails-console-with-pryrc
