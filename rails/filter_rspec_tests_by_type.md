# Filter RSpec Tests by Type

Sometimes I just want to run `model` rspec tests, or run everything except for
those slow `feature` tests in my rails app. Today I learned you can do that
with the `--tag` option.

To *only* run `model` specs:

``` shell
$ bundle exec rspec --tag type:model
```

To *exclude* `feature` specs (using the `~`):

``` shell
$ bundle exec rspec --tag ~type:feature
```

What's convenient is `rspec-rails` will infer the `type` of the spec based on
it's location in the `spec/` directory, so even if you don't explicitly tag
your tests with `type: :model` these filters will still work.

[rspec --tag option docs](https://rspec.info/features/3-13/rspec-core/command-line/tag/)
