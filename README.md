Clone this repo, `cd` into it and run

```
// Create `redis-rb` directory with a local Git dependency
// Alternatively you can use https method, it shouldn't really matter
git clone git@github.com:3scale/redis-rb.git

// Make sure the repository is checked out at a proper branch
cd redis-rb && git switch apisonator

// Install the app using local Git repo redirection that is specified
// in `app/.bundle/config`
cd ../app && bundle install
```



