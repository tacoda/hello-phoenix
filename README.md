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

```sh
$ heroku create --buildpack "https://github.com/HashNuke/heroku-buildpack-elixir.git"
$ heroku buildpacks:add https://github.com/gjaldon/heroku-buildpack-phoenix-static.git
$ heroku addons:create heroku-postgresql:hobby-dev
$ heroku config:set POOL_SIZE=18
$ mix phx.gen.secret
$ heroku config:set SECRET_KEY_BASE=""
# commit
$ git push heroku master
$ heroku run "POOL_SIZE=2 mix ecto.migrate"
```
