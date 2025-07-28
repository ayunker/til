# ActiveModel Error Details as a Hash

Today I Learned about a new way to list the errors for an invalid ActiveRecord
model. Let's say I have a blog post class with title and author attributes,
both of which are required:

``` ruby
class BlogPost < ApplicationRecord
  validates :title, presence: true
  validates :author, presence: true
end
```

Normally I interact with the errors in an invalid model through the nice
ActiveModel Errors interface:

``` ruby
pry(main)> blog_post = BlogPost.new
pry(main)> blog_post.valid?
pry(main)> blog_post.errors
# => <ActiveModel::Errors [#<ActiveModel::Error attribute=title, type=blank,
options={}>, #<ActiveModel::Error attribute=author, type=blank, options={}>]>

pry(main)> blog_post.errors.where(:title)
# => [#<ActiveModel::Error attribute=title, type=blank, options={}>]
```

But you can also return a hash of attributes containing arrays of their [error
details](https://api.rubyonrails.org/classes/ActiveModel/Errors.html#method-i-details)
and use your favorite hash methods:

```ruby 
pry(main)> blog_post.errors.details
# => {:title=>[{:error=>:blank}], :author=>[{:error=>:blank}]}

pry(main)> blog.errors.details.dig(:title, 0, :error)
# => :blank
```

via https://til.hashrocket.com/posts/eh9kdnq3iw-activemodel-error-details-as-a-hash
