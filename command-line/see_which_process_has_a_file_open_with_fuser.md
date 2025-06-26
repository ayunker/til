# See Which Process Has a File Open with fuser

Today I learned you can see which processes have a file open with `fuser`. For
example, if I wanted to see what process was writing to my rails
`log/development.log` file, I'd run

```
$ fuser log/development.log
log/development.log: 76170
```

So the process with PID 76170 has the file open. Running `ps` will show me the
process details:

```
$ ps 76170
  PID   TT  STAT      TIME COMMAND
76170 s008  S+     0:02.86 ruby bin/rails console
```

Turns out I had a `rails console` running somewhere!

You could also turn this into a one-liner with `xargs`:

```
$ fuser log/development.log | xargs ps
```

via https://til.hashrocket.com/posts/o8nas2e7rr-see-which-process-has-a-file-open-with-fuser
