# Running a Single Jest Test

Jest runs tests in parallel by default, file by file.

That means if you add a `.only` on an `it` or `describe`, that **only** applies in the context of a single file. So if you have a test suite with 5 different test files and execute tests with `jest`, 4 test files will run all their tests and one file will run it's `only` test.

If you want only a single test to run, you need to add that `.only` _and_ narrow jest's scope to that single test file: `jest src/path/to/test.js`.

via https://til.hashrocket.com/posts/viebxsyz7z-running-a-single-jest-test
