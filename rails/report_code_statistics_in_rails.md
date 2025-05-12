# Report Code Statistics in Rails

You can run `rails stats` to print out statistics around lines of code,
classes, methods, code to test ratio, etc for your rails app. It'll print out a
table like this:

```
$ bin/rails stats

+----------------------+--------+--------+---------+---------+-----+-------+
| Name                 |  Lines |    LOC | Classes | Methods | M/C | LOC/M |
+----------------------+--------+--------+---------+---------+-----+-------+
| Controllers          |    107 |     83 |       4 |      18 |   4 |     2 |
| Helpers              |      2 |      2 |       0 |       0 |   0 |     0 |
| Jobs                 |      7 |      2 |       1 |       0 |   0 |     0 |
| Models               |    126 |     55 |       4 |      10 |   2 |     3 |
| Mailers              |      4 |      4 |       1 |       0 |   0 |     0 |
| Channels             |      8 |      8 |       2 |       0 |   0 |     0 |
| Views                |    141 |    125 |       0 |       0 |   0 |     0 |
| Stylesheets          |     52 |     42 |       0 |       0 |   0 |     0 |
| JavaScript           |     30 |     16 |       0 |       0 |   0 |     0 |
| Libraries            |     62 |     56 |       0 |       0 |   0 |     0 |
| Controller tests     |      0 |      0 |       0 |       0 |   0 |     0 |
| Helper tests         |      0 |      0 |       0 |       0 |   0 |     0 |
| Model tests          |      0 |      0 |       0 |       0 |   0 |     0 |
| Mailer tests         |      0 |      0 |       0 |       0 |   0 |     0 |
| Channel tests        |     11 |      3 |       1 |       0 |   0 |     0 |
| Integration tests    |      0 |      0 |       0 |       0 |   0 |     0 |
| System tests         |      0 |      0 |       0 |       0 |   0 |     0 |
+----------------------+--------+--------+---------+---------+-----+-------+
| Total                |    550 |    396 |      13 |      28 |   2 |    12 |
+----------------------+--------+--------+---------+---------+-----+-------+
  Code LOC: 393     Test LOC: 3     Code to Test Ratio: 1:0.0
```

_(Don't mind the code to test ratio...it's a proof of concept app 😅)_

h/t Joel Hawksley, I learned about this from the excellent
[talk](https://hawksley.org/2025/02/10/lessons-from-5-years-of-ui-architecture-at-github.html)
he gave at Chicago Ruby last week.

via https://til.hashrocket.com/posts/xuh7qqdr9b-report-code-statistics-in-rails
