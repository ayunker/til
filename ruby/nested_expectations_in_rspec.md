# Nested Expectations in RSpec

Today I learned you can write nested expectations in `rspec`. I find this is
approach super useful with writing request-style tests where I want to ensure
the request returned successfully and also ensure the expected effects
happened.

``` ruby
it "creates the post" do
  expect {
    expect(request.response_code).to eq(200)
  }.to change { Post.count }.by(1)
end
```

If either the response is not a 200, or the Post count doesn't change, then the
test fails.

There is a gotcha that I run into when I build these tests iteratively - first
the inner expectation on it's own, wrap it in the outer block, and then add the
outer matcher. If you wrap the inner request in an expect block, but don't have
any assertions on that block, it will always pass - because we're not matching
against anything.

``` ruby
RSpec.describe do
  # ❌ - as expected
  it do
    expect(true).to eq(false)
  end

  # ❌ - as expected, outer expectation passes but inner fails, so the test fails
  it do
    expect {
      expect(true).to eq(false)
    }.to not_change { 0 }
  end

  # ✅ - :-? watch out for this one, even though the inner expectation fails, the test passes
  it do
    expect {
      expect(true).to eq(false)
    }
  end
end
```

via https://til.hashrocket.com/posts/eb47vykelq-nested-expectations-in-rspec
