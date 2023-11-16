# Mock External Library Functions in Jest

Suppose you import two functions from an external library in one of your js files:

```javascript
import { func1, func2 } from "externalLib";

export const doSomething = () => {
  func1();
  func2();
  // ...
};
```

Now let's write a test for this function, and say we want to mock `func1`.

```javascript
describe("doSomething", () => {
  jest.mock("externalLib", () => ({
    func1: jest.fn(),
  }));

  it("does something", () => {
    func1.mockImplementation(...);
    // ...
  });
});
```

But oh no! This test will fail - we inadvertently blew away the rest of the implementation of `externalLib` when we created the mock for `func1`. Since `doSomething` relies on other functions in `externalLib`, we get errors.

In order to preserve the rest of the implementation of `externalLib` and only mock `func1`, we need to call [requireActual](https://jestjs.io/docs/jest-object#jestrequireactualmodulename) and spread it's return into the mock to get the implementation of the rest of the library:

```javascript
describe("doSomething", () => {
  jest.mock("externalLib", () => ({
    ...jest.requireActual("externalLib"),
    func1: jest.fn(),
  }));

  it("does something", () => {
    func1.mockImplementation(...);
    // ...
  });
});
```

Et voilà, your test will pass ✅.

via https://til.hashrocket.com/posts/iz1v6cdqu0-mock-external-library-functions-in-jest
