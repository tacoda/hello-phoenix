# Hello

To start your Phoenix server:

  * Install dependencies with `mix deps.get`
  * Create and migrate your database with `mix ecto.setup`
  * Install Node.js dependencies with `cd assets && npm install`
  * Start Phoenix endpoint with `mix phx.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](https://hexdocs.pm/phoenix/deployment.html).

## Learn more

  * Official website: http://www.phoenixframework.org/
  * Guides: https://hexdocs.pm/phoenix/overview.html
  * Docs: https://hexdocs.pm/phoenix
  * Mailing list: http://groups.google.com/group/phoenix-talk
  * Source: https://github.com/phoenixframework/phoenix

## Deploying on Heroku

https://hexdocs.pm/phoenix/heroku.html

```sh
$ heroku create --buildpack hashnuke/elixir
$ heroku buildpacks:add https://github.com/gjaldon/heroku-buildpack-phoenix-static.git
$ heroku addons:create heroku-postgresql:hobby-dev
$ heroku config:set POOL_SIZE=18
$ mix phx.gen.secret
$ heroku config:set SECRET_KEY_BASE=""
# commit
$ git push heroku master
$ heroku run "POOL_SIZE=2 mix ecto.migrate"
# limit the pool size for any task
# heroku run "POOL_SIZE=2 mix hello.task"
# connect to the dyno
$ heroku ps:exec
# launch iex session
# TODO: Figure this one out
$ iex --sname console -remsh server@${HOSTNAME}
$ heroku logs --tail
$ heroku run "POOL_SIZE=2 iex -S mix"
```

If you are constantly getting connection timeouts while running `heroku run` this could mean that your internet provider has blocked port number 5000. You can overcome this by adding `detached` option to run command:

```sh
$ heroku run:detached "POOL_SIZE=2 mix ecto.migrate"
```
