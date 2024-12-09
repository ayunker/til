# RSpect expect not_to change from

I use the [rspec change
matcher](https://rubydoc.info/gems/rspec-expectations/RSpec%2FMatchers:change)
a lot to check the before and after values of something while the subject under
test executes. A convoluted example:

``` ruby
RSpec.describe "expect change from to" do
  it do
	x = 1
    expect{ x = x + 1 }.to change { x }.from(1).to(2)
  end
end
```

And sometimes I use to it to verify something *doesn't* change.

``` ruby
RSpec.describe "expect not to change" do
  it do
	x = 1
    expect{ nil }.not_to change { x }
  end
end
```

Which is great - but sometimes I want to make sure my understanding of the
initial state is correct and want to verify it didn't change *from* its initial
value - in this case 1.

``` ruby
RSpec.describe "expect not to change from" do
  it do
	x = 1
    expect{ nil }.not_to change { x }.from(1)
  end
end
```

And if that `from` value is wrong, I'll get a nice message explaining what's
wrong.

``` ruby
RSpec.describe "expect not to change from" do
  it do
	x = 1
    expect{ nil }.not_to change { x }.from(0)
  end
end
# => expected `x` to have initially been 0, but was 1
```

via https://til.hashrocket.com/posts/f8c8xydnph-rspec-expect-notto-change-from
