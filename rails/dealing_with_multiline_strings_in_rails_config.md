# Dealing with Multiline Strings in Rails Config

Say I have a multiline string for an environment variable

``` ruby
MY_VAR="hi
bye"
```

If I try to import that in a Rails config yml file, I'm going to have a bad time.

``` ruby
config:
  my_value: <%= ENV.fetch("MY_VAR") %>
```

If this config file is autoloaded, rails will blow up on startup:

```
YAML syntax error occurred while parsing config.yml. Please note that YAML must be consistently indented using spaces. Tabs are not allowed. Error: (<unknown>): could not find expected ':' while scanning a simple key at line 15 column 1 (Psych::SyntaxError)
```

This is happening because the ERB output is not writing the line breaks in a way that Psych (ruby YAML parser) knows how to handle. We can use `String#dump` to return the quoted version of the string to make Psych happy.

``` ruby
"hi
bye".dump

=> "\"hi\\nbye\""
```

So the resulting config would look like so:

``` ruby
config:
  my_value: <%= ENV.fetch("MY_VAR").dump %>
```

And then our app can start and in console:

``` ruby
Rails.configuration.config.my_value

=> "hi\nbye"
```

via https://til.hashrocket.com/posts/t0ylftuopi-importing-multiline-strings-in-rails-config
