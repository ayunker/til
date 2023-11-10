# 414 URI Too Long

Today I learned that sometimes a URI can be too long. There's no a set length - it can vary by server, and some might not even enforce it - but it can happen. And when it does, you'll get a `414 - URI Too Long`.

So next time you sling a long array of ids into a query string, beware the `414`.

[Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/414)

[RFC](https://datatracker.ietf.org/doc/html/rfc7231#section-6.5.12)

via https://til.hashrocket.com/posts/fcz1lrkiv9-414-uri-too-long
