# Filter Fields and Associations When Rendering JSON

Today I learned you can modify a json payload in a rails controller to include
associated models and filter attributes in the payload with the `include` and
`only` options.

Say I have a controller that returns all blog `Post` records as json:

``` ruby
def index
  respond_to do |format|
    format.json do
      render json: Post.all
    end
  end
end
```

Now, say I want to include attributes for an associated `Author` model, but
only their first and last name and exclude all other attributes. I can
`include` the authors, and `only` include first and last name:

``` ruby
def index
  respond_to do |format|
    format.json do
      render json: Post.all, include: {author: {only: [:last_name, :first_name]}}
    end
  end
end
```

via https://til.hashrocket.com/posts/cneh3c3ow5-filter-fields-and-associations-when-rendering-json
