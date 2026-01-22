# Get Whodunnit Instance from PaperTrailGlobalId

I ran into an issue trying to get an instance of the `User` who made a change
captured by [paper_trail](https://github.com/paper-trail-gem/paper_trail) with
the [paper_trail-globalid](https://github.com/ankit1910/paper_trail-globalid)
gem.

With regular `paper_trail`, calling `whodunnit` will give you the id or name of
the user who... dunnit.

``` ruby
post.versions.last.whodunnit
# => "Tony Yunker"
```

With the
[paper_trail-globalid](https://github.com/ankit1910/paper_trail-globalid) gem,
whodunnit is saved as, well, a global id.

```ruby
post.versions.last.whodunnit
# => "gid://app/User/12345"
```

This isn't super helpful on it's own, but `actor` will resolve the global id
and return an instance of the model it references.

```ruby
post.versions.last.whodunnit
# => <User:0x000000015d618010...>
```

via https://til.hashrocket.com/posts/zyaljswzpx-get-whodunnit-instance-from-papertrailglobalid
