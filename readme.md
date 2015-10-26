learning Laravel with Heroku

以下を実行して作成

```bash
$ curl -sS https://getcomposer.org/installer | php
$ ./composer.phar create-project laravel/laravel --prefer-dist learn-laravel-heroku
$ cd learn-laravel-heroku
$ echo "web: vendor/bin/heroku-php-apache2 public/" > Procfile
$ git init
$ git add .
$ git commit -m 'init'
$ heroku create
$ heroku buildpacks:set https://github.com/heroku/heroku-buildpack-php
$ heroku config:set APP_KEY=$(php artisan key:generate --show)
$ git push heroku master
$ heroku open
```

以下でデプロイ可能(多分)

```bash
$ git clone https://github.com/tetor/learn-laravel-heroku.git
$ cd learn-laravel-heroku
$ heroku login
$ heroku create
$ heroku buildpacks:set https://github.com/heroku/heroku-buildpack-php
$ heroku config:set APP_KEY=$(php artisan key:generate --show)
$ git push heroku master
$ heroku open
```
