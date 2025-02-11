# ActiveSupport Inflections - humanize vs titleize

ActiveSupport has a lot of useful
[inflections][]
to transform strings, and I often forget which one does what exactly.

`# humanize` will capitalize the first
[word][],
whereas `#titleize` will capitalize every word:

``` ruby
"hi_how_are_you?".humanize
# => "Hi how are you?"

"hi_how_are_you?".titleize
# => "Hi How Are You?"

```

Actually, it turns out `#titleize` is just a [special
case][]
of `#humanize`!

via [Today I Learned](https://til.hashrocket.com/posts/vxxtceyntx-activesupport-inflections-humanize-vs-titleize)



[inflections]: https://github.com/rails/rails/blob/v8.0.1/activesupport/lib/active_support/core_ext/string/inflections.rb
[word]: https://github.com/rails/rails/blob/main/activesupport/lib/active_support/inflector/methods.rb#L146
[special_case]: https://github.com/rails/rails/blob/main/activesupport/lib/active_support/inflector/methods.rb#L192
