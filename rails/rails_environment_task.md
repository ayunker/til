# Rails Environment Task

In a Rails task if you need to load in your rails application (to get access to
your models, etc.), you have to call `:environment` in the task:

``` ruby
task task_name: :environment do 
  ...
end
```

I kind of always took this for granted, and never thought much about it. Then,
in [Xavier Noria's 2024 Rails World
talk](https://www.youtube.com/watch?v=Kx0ihLCTEgE) he mentioned that
`:environment` itself is a task - and that syntax is actually saying your task
depends upon `:environment` and run that task before your task runs. 🤯

So I decided to look up what the [environment task actually
does](https://github.com/rails/rails/blob/main/railties/lib/rails/application.rb#L561):

``` ruby
task :environment do
  ActiveSupport.on_load(:before_initialize) { config.eager_load = config.rake_eager_load }

  require_environment!
end
```

`require_environment!` ... requires your environment, specifically it
`require`s your `config/environment.rb` which runs
`Rails.application.initialize!` - which is what actually starts your rails app.

Cool!

via https://til.hashrocket.com/posts/13vosilvmg-rails-environment-task
