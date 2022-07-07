# Install Postgres Ruby Gem on M1

I'm not sure if this is because I installed via PostgresApp.com or what, but I
was unable to build the `pg` gem on an M1 Mac without installing additional
libraries.

Gem install failed, so needed to do the following to get all the necessary
libs. `libpq` is all the C libraries for PG. Not 100% sure why whats in
PostgresApp isn't enough?

``` brew install libpq echo 'export PATH="/opt/homebrew/opt/libpq/bin:$PATH"'
>> /Users/tyunker/.bash_profile ```

Once installed and added to PATH, gem install should succeed.
