# Easily Update ActiveRecord Enum Values

Today I learned about some nice helper methods for [ActiveRecord Enums](https://api.rubyonrails.org/classes/ActiveRecord/Enum.html). You might already know the `?` methods to check the value of the enum. There are also `!` methods to succinctly set the value of the enum too!

```ruby
class Post < ActiveRecord::Base
  enum status: {
    draft: 0,
    published: 1
  }
end

post = Post.new
post.published? # => false
post.published! # updates the status to `published`
post.published? # => true
```

via https://til.hashrocket.com/posts/rhaurpd3vk-easily-update-activerecord-enum-values
