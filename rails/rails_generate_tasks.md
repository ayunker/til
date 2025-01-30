# Rails Generate Tasks

[Andrew's
TIL](https://til.hashrocket.com/posts/uzlxeusneu-rails-8-generate-one-off-scripts)
from the other day got me thinking about rails generators, and I never knew
there was a generator for rake tasks!

There's not a ton of boilerplate in rake tasks, but that's never stopped me
from making a typo.

`bin/rails g task hello` will generate just the namespace `hello`

``` ruby
# lib/tasks/hello.rake
namespace :hello do
end
```

If you have one or more tasks within the namespace, you can include them and
the generator will add a `task` for each one:

`bin/rails g task say hi bye good_day` will generate

``` ruby
# lib/tasks/say.rake
namespace :say do
  desc "TODO"
  task hi: :environment do
  end

  desc "TODO"
  task bye: :environment do
  end

  desc "TODO"
  task good_day: :environment do
  end
end
```

via https://til.hashrocket.com/posts/mqt7btxsdr-rails-generate-tasks
