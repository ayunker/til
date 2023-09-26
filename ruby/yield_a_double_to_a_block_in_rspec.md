# Yield a double to a Block in RSpec

TIL in rspec you can yield a double to a block with `and_yield`, similar to how you return a double with `and_return`.

With `and_return` you can write a test like this:

``` ruby
sftp = Net::SFTP.start(args)
sftp.upload!(content, path)

# Test
client = double
allow(Net::SFTP).to receive(:start).and_return(client)
expect(client).to receive(:upload!)
```

However, if your code has a block like below `and_return` won't work. Instead, you can use `and_yield` to yield the double to the block:

``` ruby
Net::SFTP.start(args) do |sftp|
  sftp.upload!(content, path)
end

# Test
client = double
allow(Net::SFTP).to receive(:start).and_yield(client)
expect(client).to receive(:upload!)
```

[Docs](https://rspec.info/documentation/3.12/rspec-mocks/RSpec/Mocks/MessageExpectation.html#and_yield-instance_method)

via https://til.hashrocket.com/posts/hd5ofx8f2c-yield-a-double-to-a-block-in-rspec
