# Bundle Pristine

Bundler has a `pristine` option, which will reset all gems in your lock file to their pristine state, from RubyGems or git or wherever your gems come from.

```
bundle pristine
```

This is similar to `gem pristine --all`, but the key difference is this will pristine all gems installed, whereas `bundle pristine` is scooped to those in `Gemfile.lock`.

(If you want to reset a single gem, you can run `gem pristine [gem_name]`, but I can never remember which/how many gems I've mucked about with)

[Docs](https://bundler.io/v2.4/man/bundle-pristine.1.html)
