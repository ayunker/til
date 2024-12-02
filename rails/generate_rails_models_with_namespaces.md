# Generate Rails Models with Namespaces

You can use the rails model generator to generate namespaced models. I always
have a hard time remembering the syntax for namespaces, but it's pretty
straightforward.

Say I want to create a model `Blog::Post`. The generator for this is:

```
rails generate model blog/post title:string ...
```

This will generate the following files (assuming you're using rspec and
FactoryBot)

```
invoke  active_record
create    db/migrate/20241028193321_create_blog_posts.rb
create    app/models/blog/post.rb
create    app/models/blog.rb
invoke    rspec
create      spec/models/blog/post_spec.rb
invoke      factory_bot
create        spec/factories/blog/posts.rb

```

If the namespace already exists, you'll be prompted to either overwrite or keep
the existing `app/models/blog.rb` file (you'll probably want to keep the
existing one).

Happy generating!

via https://til.hashrocket.com/posts/hdhkabgrg0-generate-rails-models-with-namespaces
