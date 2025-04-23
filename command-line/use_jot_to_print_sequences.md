# Use jot to Print Sequences

Today I Learned about [`jot`](https://manpages.org/jot) a command line utility
that prints sequential or random data. Let's focus on the sequential bit:

`jot` takes arguments for `reps`, `begin` and `end`. So if we wanted to print
the integers from 1 to 10, we'd do:

``` sh
$ jot - 1 10
1
2
3
4
5
6
7
8
9
10
```

Which is neat, but only so cool. What if we wanted to print 21 evenly spaced
numbers between -1 and 1? That would be cooler:

``` sh
$ jot 21 -1 1.00 #the 1.00 tells the output to be float, not int
-1.00
-0.90
-0.80
-0.70
-0.60
-0.50
-0.40
-0.30
-0.20
-0.10
-0.00
0.10
0.20
0.30
0.40
0.50
0.60
0.70
0.80
0.90
1.00
```

You can even print all the ASCII characters with:

``` sh
jot -c 128 0
1
2
3
4
5
6
7
8
9
:
;
<
=
>
?
@
A
B
C
...
```

via https://til.hashrocket.com/posts/7xxzwqpzhs-use-jot-to-print-sequences
