# Get Arrays Min and Max with minmax

In ruby, you can get the minimum value in an array with `#min` and the maximum
value with `#max`. 

But sometimes you need both the min and max, and it feels a waste to make two
separate calls. Turns out you can get both in one with `#minmax` - which will
return a two element array with the min and max values.

``` ruby
pry(main)> [1, 2, 3].minmax
# => [1, 3]
```

You can also pass it a block for custom ordering criteria.

[Docs](https://ruby-doc.org/3.4.1/Enumerable.html#method-i-minmax)

via https://til.hashrocket.com/posts/uodz90rbg0-get-arrays-min-and-max-with-minmax
