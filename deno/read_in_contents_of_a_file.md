# Read in Contents of a File

To read in a file in Deno, you can use Deno's `readTextFile`

``` typescript
const input: string = await Deno.readTextFile("./example/input.txt")
```

You need to explicitly enable file reading when running the file with the
`--allow-read` flag.

``` bash
deno run --allow-read index.ts
```

[Ref](https://deno.land/manual@v1.14.0/examples/read_write_files)
