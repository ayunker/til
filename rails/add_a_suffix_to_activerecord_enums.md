# Add a Suffix to ActiveRecord Enums

Today I learned you can add suffixes to ActiveRecord Enums. I knew it was
possible to prefix enums with the `_prefix` option:

``` ruby
class Answer < ApplicationRecord
  enum selection: {yes: "yes", no: "no", idk: "i don't know"}, _prefix: true
end
```

And you get helper methods like `answer.selection_yes?`, but that reads a
little awkwardly. I'd like it better if I could do `answer.yes_selection?`.
Turns out you can, with `_suffix`:

``` ruby
class Answer < ApplicationRecord
  enum selection: {yes: "yes", no: "no", idk: "i don't know"}, _suffix: true
end

answer = Answer.new selection: "yes"
answer.yes_selection? # => true
answer.no_selection? # => false
```

[ActiveRecord::Enum Docs](https://edgeapi.rubyonrails.org/classes/ActiveRecord/Enum.html)

via https://til.hashrocket.com/posts/xifpryoow0-add-a-suffix-to-activerecord-enums
