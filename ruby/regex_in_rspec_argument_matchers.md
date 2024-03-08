# Regex in RSpec Argument Matchers

Today I learned you can use regular expressions in RSpec method argument
expectations.

Suppose I have a method that takes an email, and a registered boolean as
parameters:

``` ruby
def some_method(email:, registered:)
end
```

In a spec, it's easy enough to verify that it was called with set parameters,
like `test@example.com` and `true`:

``` ruby
expect(subject).to receive(:some_method).with(email: 'test@example.com', registered: true)
```

But what if I want to verify that the email address just belongs to
`example.com`? We can use a regex for that!

``` ruby
expect(subject).to receive(:some_method).with(email: /@example.com$/, registered: true)
```

Ref: https://rspec.info/documentation/3.7/rspec-mocks/RSpec/Mocks/ArgumentMatchers.html
