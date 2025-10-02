# Ensure Correct Redirect Action with 303 Status Code

Let's say I have a `Post` model, and send a `PATCH` XHR request for an instance
of `Post`, handled by the `PostsController`. Normally, if I want to redirect to
the `posts_path` in that controller action I end the method like so:

``` ruby
def patch
  # patch-y things done here
  redirect_to posts_path
end # => redirects to PATCH /posts ❌
```

It's possible, depending on your browser, that instead of redirecting as a
`GET` request to `posts_path` like you would expect, the original `PATCH`
method is forwarded instead. Most times, this probably isn't what you want. To
force the redirect to use the appropriate method for the path you're
redirecting to, you can use the `303 See Other` status code:

``` ruby
def patch
  # patch-y things done here
  redirect_to posts_path, status: :see_other
end # => redirects to GET /posts ✅
```

It's specifically called out in the docs
([ActionController::Redirecting](https://api.rubyonrails.org/classes/ActionController/Redirecting.html#method-i-redirect_to))
so it seems to be fairly well-known/widespread, but it was a new to me
occurrence.

via https://til.hashrocket.com/posts/pvbvgoxp2r-ensure-correct-redirect-action-with-303-status
