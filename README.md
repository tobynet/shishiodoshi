# Shishiodoshi

!(Shishi-odoshi)[https://gist.githubusercontent.com/toooooooby/9172769/raw/7aa3fefd4fb0a00ab91f9fad6f46545dfb6ee4ce/shishiodoshi_image.gif]

Daily Restarter for Travis-CI.

The first motivation: 

    > Test own projects of rubygems on a daily basis without any commitings.

## Getting Started

Run for Test.

```bash
$ git clone https://github.com/toooooooby/shishiodoshi
$ cd shishiodoshi

$ cp config.yml.example config.yml
$ # Edit config.yml ...

# run for running
$  TRAVIS_TOKEN="YOUR_TRAVIS_TOKEN" rake
```

Run on heroku.

```bash
$ heroku login
$ heroku apps:create shishiodoshi

$ cp config.yml.example config.yml
$ # edit config.yml ...
$ git add . && git ci -m 'Make config.yml'

$ git push heroku master

$ heroku config:add TRAVIS_TOKEN="YOUR_TRAVIS_TOKEN"
$ heroku run rake

# Settings for scheduler
$ heroku addons:add scheduler:standard
$ heroku addons:open scheduler
```

## refs.

* [travis-ci/travis](https://github.com/travis-ci/travis#table-of-contents)
* [Travis-CIのビルドをherokuから繰り返し実行する - Qiita](http://qiita.com/sawanoboly/items/7f275e20fb6a643a3553)


