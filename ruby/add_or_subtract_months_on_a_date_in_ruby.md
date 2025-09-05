# Add/Subtract Months on a Date in Ruby

With `ActiveSupport` you can easily add months (or days, years, etc) to a date
with:

``` ruby
pry(main)> Date.today
# => Fri, 05 Sep 2025
pry(main)> Date.today + 2.months
# => Wed, 05 Nov 2025
pry(main)> Date.today - 1.month
# => Tue, 05 Aug 2025
```

But what if you're working outside of Rails and without `ActiveSupport`? You
can use the shovel (`<<`) operator on dates to return the date `n` months
earlier.

``` ruby
pry(main)> Date.today
# => Fri, 05 Sep 2025
pry(main)> Date.today << 1
# => Tue, 05 Aug 2025
```

If you want to go forwards, you can use `>>`, or negate the value of `n` using
`<<`:

 ``` ruby
pry(main)> Date.today
# => Fri, 05 Sep 2025
pry(main)> Date.today >> 2
# => Wed, 05 Nov 2025
pry(main)> Date.today << -2
# => Wed, 05 Nov 2025
```

[Docs for `<<`](https://docs.ruby-lang.org/en/master/Date.html#method-i-3C-3C)
and [docs for
`>>`](https://docs.ruby-lang.org/en/master/Date.html#method-i-3E-3E)

via https://til.hashrocket.com/posts/k1tbzp6geo-addsubtract-months-on-a-date-in-ruby
