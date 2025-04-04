# Javascript's Unary Plus Operator


Today I learned about the unary plus (`+`) operator. It attempts to convert its
operand into a number, so it's basically a shorthand for `Number()` (and uses
the same rules around number coercion).

``` js
+5
// 5
+"7"
// 7

+true
// 1
+false
// 0
+null
// 0
+undefined
// NaN
+[]
// 0
```


[Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unary_plus)

via https://til.hashrocket.com/posts/vxix2upqaj-javascripts-unary-plus-operator
