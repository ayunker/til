# Search Through Git Log

There are a number of ways to search through git history:

Return all commits matching, output in patch format
```
git log -p -G ThingForWhichToSearch
```

Return all commits matching, output commit sha and title
```
git log -G ThingForWhichToSearch
```

`-p`: display git log with full patch
`-G`: grep through log (includes commit title, message, patch)

There are probably a million other ways to compose this, but this is a start.

h/t Jack Christensen
