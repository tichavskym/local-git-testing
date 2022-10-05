# Instructions to reporoduce

```
// Clone this repository and `cd` into it
git clone git@github.com:tichavskym/local-git-testing.git && cd local-git-testing

// Create `redis-rb` directory with a local Git dependency
// Alternatively you can use https method, it shouldn't really matter
git clone git@github.com:3scale/redis-rb.git

// Make sure the repository is checked out at a proper branch
cd redis-rb && git switch apisonator

// Install the app using local Git repo redirection that is specified
// in `app/.bundle/config`
cd ../app && bundle install
```

This will return an error. Replacing first line of `redis-rb/redis.gemspec` 
(path from root of this repository) with the following lines (or something similar):

```
lib = File.expand_path('../lib', __FILE__)
$LOAD_PATH.unshift(lib) unless $LOAD_PATH.include?(lib)
require "redis/version" 
```

will make it work.
