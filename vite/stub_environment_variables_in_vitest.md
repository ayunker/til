# Stub Environment Variables in Vitest

You can stub environment variables in [Vitest](https://vitest.dev/) using `vi.stubEnv`. This will stub the value on `process.env` and `import.meta.env`.

You can also reset all env vars back to their original value with `vi.unstubAllEnvs`.

``` js
process.env.COOL_ENV_VAR; // => "test"
import.meta.env.COOL_ENV_VAR; // => "test"

vi.stubEnv('COOL_ENV_VAR', "stubbed");

process.env.COOL_ENV_VAR; // => "stubbed"
import.meta.env.COOL_ENV_VAR; // => "stubbed"

vi.unstubAllEnvs();

process.env.COOL_ENV_VAR; // => "test"
import.meta.env.COOL_ENV_VAR; // => "test"

```

[Docs](https://vitest.dev/api/vi.html#vi-stubenv)

via https://til.hashrocket.com/posts/ghwn4zzhj4-stub-environment-variables-in-vitest
