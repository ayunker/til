# RSpec's be_within Matcher

Today I learned RSpec has a [be_within
matcher](https://www.rubydoc.info/github/rspec/rspec-expectations/RSpec%2FMatchers%3Abe_within).

It kinda does what it says - it verifies if the actual is within a delta (`<=`)
of the expected. 

``` ruby
expect(3.0).to be_within(0.5).of(3.0) # ✅
expect(3.2).to be_within(0.5).of(3.0) # ✅
expect(3.5).to be_within(0.5).of(3.0) # ✅
expect(4.3).to be_within(0.5).of(3.0) # ❌ 
```

via https://til.hashrocket.com/posts/ja7i40tec3-rspecs-bewithin-matcher
