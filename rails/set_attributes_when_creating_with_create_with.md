# Set Attributes when Creating with .create_with

You can set attributes to be used when creating new records with `.create_with`:

``` ruby
Author.create_with(name: "Hashrocketeer")
Author.new.name # => "Hashrocketeer"
```

This can be particularly useful if you're doing a `.find_or_create_by` and want to set some values only when creating:

``` ruby
Author
  .create_with(post_count: 0)
  .find_or_create_by(name: "Hashrocketeer")
```

This will find an author with name "Hashrocketeer". If we find an existing `Author`, we won't change their `post_count`. If we don't find an existing `Author`, we'll create one with a `post_count` of 0. 

Docs: https://api.rubyonrails.org/classes/ActiveRecord/QueryMethods.html#method-i-create_with

via: https://til.hashrocket.com/posts/hqqltwuka8-set-attributes-when-creating-with-createwith
