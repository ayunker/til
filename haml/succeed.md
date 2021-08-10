# Succeed (and Precede and Surround)

Haml has helper methods to handling punctuation after html markup. Other uses abound, but this is my main use.

Say you have a link and immediately after want a period (outside of the href).
```
=link_to 'Click here', path
\.

=> <a>Click here</a> .
```

The above yields an unpleasant space between the closing `a` tag and  the punctuation. `succeed` fixes that:

```
=succeed '.' do
  =link_to 'Click here', path

=> <a>Click here</a>.
```

Magic!

Precede and Surround behave similarly.

Ref: [HAML docs](https://haml.info/docs/yardoc/file.REFERENCE.html#succeed)
h/t [Hashrocket TIL entry](https://til.hashrocket.com/posts/3816f30c71-succeed-precede-and-surround-in-haml)
