# Silence Logging in Console

Sometimes in `rails console`, you don't want all the ActiveRecord related logging that comes out. Particularly if operating on a big hash, or enqueuing thousands of jobs.

You can temporarily silence output by wrapping in LoggerSilence block

```
ActiveRecord::Base.logger.silence do
  &block
end
```

or

```
ActiveRecord::Base.logger.silence { &block }
```
