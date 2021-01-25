A simple buildpack that posts a deploy message to slack via `SLACK_DEPLOYMENT_WEBHOOK_URL`.

Useful with both Gigalixir and Heroku.

To add this buildpack to Gigalixir, you need a `.buildpacks` file. For example, if you are using mix

```
https://github.com/gigalixir/gigalixir-buildpack-clean-cache.git
https://github.com/HashNuke/heroku-buildpack-elixir
https://github.com/gjaldon/heroku-buildpack-phoenix-static
https://github.com/gigalixir/gigalixir-buildpack-mix.git
https://github.com/flexibility-org/buildpack-webhook.git
```

Then set the url to curl, for example

```
gigalixir config:set -a $APP_NAME SLACK_DEPLOYMENT_WEBHOOK_URL="https://www.google.com"
```

To get better deploy messages, such as current HEAD's commit message, you'll need to set the following env vars:

```
DEPLOY_NOTIFY_GITHUB_AUTH_TOKEN
DEPLOY_NOTIFY_GITHUB_ORG
DEPLOY_NOTIFY_GITHUB_PROJECT
```

Adapted from https://github.com/evantahler/heroku-buildpack-notify-slack-deploy
