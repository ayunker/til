# Rerun Only Failed Tests in RSpec

Today I learned about rspec's `--next-failure` (`-n`) flag.

Say you run your entire rspec suite and a couple of tests fail. You make a change that should fix them. How can you quickly rerun those failed tests to see if they're green? It could take minutes to run the whole suite again, and all you care about is 2 tests. 

That's where the `--next-failure` (`-n`) flag comes in handy. According to the docs it is "Equivalent to `--only-failures --fail-fast --order defined`)". So you can rerun only your failed specs, and exit immediately if one does fail. You could of course just [use `--only-failures`](https://til.hashrocket.com/posts/2ab099c7e8-rerun-only-failures-with-rspec) too, but sometimes it's nice to fail fast.

``` sh
bundle exec rspec -n
```

h/t [Brian Dunn](https://til.hashrocket.com/authors/briandunn)
via https://til.hashrocket.com/posts/2ymmxa29ua-rerun-only-failed-tests-with-rspec
