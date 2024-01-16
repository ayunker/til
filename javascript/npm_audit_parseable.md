# Parseable npm audit output

In `npm` v6 and below, `npm audit` has a `--parseable` option that will output
the audit report in plain text rows with tab delimiters. By default, its a lot
of information, but you can `awk` and `grep`/`ripgrep` to parse and filter down
to what you want.

To only print the package name, vulnerability level and resolution, you can run:

```
% npm audit --parseable | awk -F $'\t' '{print $2, $3, $4}'

minimist critical npm update minimist --depth 15
immer high npm install
loader-utils high npm install react-scripts@5.0.1
decode-uri-component high npm install react-scripts@5.0.1
```

And you can pipe that through to `ripgrep` to only show the `critical`
vulnerabilities.

```
% npm audit --parseable | awk -F $'\t' '{print $2, $3, $4}' | rg critical

minimist critical npm update minimist --depth 15
```

In newer versions of `npm`, the `--parseable` option was dropped and instead you
can use the `--json` option to output to json.

via https://til.hashrocket.com/posts/3vw2or0eqg-parseable-npm-audit-output
