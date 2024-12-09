# RSpec Comparison Operators

You can use comparison operators like `<`, `<=`, `>`, and `>=` (and more!) in rspec tests:

``` ruby
RSpec.describe "Comparison Operators" do
  it do
    expect(5).to be < 7
    expect(5).to be >= 5
  end
end
```

* [Docs](https://rspec.info/features/3-12/rspec-expectations/built-in-matchers/comparisons/)

via https://til.hashrocket.com/posts/256je0dkww-rspec-comparison-operators
