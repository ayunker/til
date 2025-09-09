# Create New Rails App with Old Rails Version

Sometimes you need to spin up a rails app using an older version of rails.
Running `rails new` will spin up an app with the latest version (which is what
you want most of the time). But if you have older gems of rails installed you
can create new rails apps by specifying the version wrapped in underscores. 

Say your `rails` entry in your `gem list` looks like this: `rails (7.2.2.2,
7.2.1, 7.1.5.2, 7.1.2, 7.0.8.7)`. If you want to create a new rails app using
`7.0.8.7`, you can run (`_` before *and* after the version number!):

``` sh
rails _7.0.8.7_ new new_app
```

And boom, you've got a `new_app` created running rails 7.0.8.7.

via https://til.hashrocket.com/posts/vcqlvlytux-create-new-rails-app-with-old-rails-version
