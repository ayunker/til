# Limit Jest Test Coverage

Jest allows you to [view test coverage when it runs](https://til.hashrocket.com/posts/fwoye7lps4-test-coverage-stats-with-jest). 

But even if I only run tests for a specified file or files, the `--coverage` output will include all files. 

```
jest src/directoryToTest --coverage
```

If your app is large, this can generate a lot of output and be difficult to parse. If I only care about the coverage for files in `directoryToTest`, I can filter the output of `--coverage`  with `--collectCoverageFrom=`:

```
jest src/directoryToTest --coverage --collectCoverageFrom="src/directoryToTest/**"
```

[docs](https://jestjs.io/docs/cli#--collectcoveragefromglob)
