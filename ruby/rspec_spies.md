# RSpec Spies🕵️‍♀️

Most of the time when I write an RSpec test to see if a message was received, I'll write the expectation first using a mock, then exercise the subject under test:

``` ruby
class SomeJob
  def perform
    SomeService.call
  end

end

Rspec.describe SomeJob do
  it "makes the call" do
    expect(SomeService).to receive(:call)
    SomeJob.new.perform
  end
end
```

Sometimes it's useful to flip this around, with the expectation after the action was performed. We can do this with a spy - we first stub the call with `allow`, exercise the subject under test, then assert with `have_received`:

``` ruby
class SomeJob
  attr_reader :some_attribute

  def perform
    set_an_instance_var
    SomeService.call(some_attribute)
  end

  def set_an_instance_var
    @some_attribute = :something
  end
end

Rspec.describe SomeJob do
  subject { SomeJob.new }

  it "makes the call with an argument" do
    allow(SomeService).to receive(:call)
    subject.perform
    expect(SomeService).to have_received(:call).with(subject.some_attribute)
  end
end
```

This is particularly useful if you want to assert against something (say an instance variable) that doesn't get set until the subject is exercised. There's no way to test the above example with the assertion first, since we won't know what `some_attribute` is until we `perform` - a perfect use case for a spy.

h/t [Matt Polito](https://til.hashrocket.com/authors/mattpolito)

via https://til.hashrocket.com/posts/0t6wcigncf-rspec-spies-
