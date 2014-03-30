# Shishiodoshi

![Shishi-odoshi(the original image is public domain,http://commons.wikimedia.org/wiki/File:Shishiodoshi.gif)](https://gist.githubusercontent.com/toooooooby/9172769/raw/7aa3fefd4fb0a00ab91f9fad6f46545dfb6ee4ce/shishiodoshi_image.gif)

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
$ travis token

Your access token is XXXXXXXXXXXXXXXXXXXXXXX
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
```

At last, please configure addon's scheduler.

```
$ heroku addons:add scheduler:standard
$ heroku addons:open scheduler
```


# Examples

For example on `heroku addons:open scheduler`:

![Scheduler Example](https://gist.githubusercontent.com/toooooooby/9172769/raw/668a7c1f57165153dda1de221a504172a4c8648d/shishiodoshi-heroku-scheduled-jobs.jpg)

Results on travis monitor on CLI:

```bash
$ travis monitor -m
Monitoring 26 repositories:

2014-02-24 01:XX:XX toooooooby/kagami#15 started
2014-02-24 01:XX:XX toooooooby/kagami#15.3 started
2014-02-24 01:XX:XX toooooooby/kagami#15.2 started
2014-02-24 01:XX:XX toooooooby/yazawa#9 started
2014-02-24 01:XX:XX toooooooby/yazawa#9.1 started
2014-02-24 01:XX:XX toooooooby/yazawa#9.2 started
2014-02-24 01:XX:XX toooooooby/kagami#15.1 started
2014-02-24 01:XX:XX toooooooby/kagami#15.3 passed
2014-02-24 01:XX:XX toooooooby/kagami#15.2 passed
2014-02-24 01:XX:XX toooooooby/kagami#15 passed
2014-02-24 01:XX:XX toooooooby/kagami#15.1 passed
2014-02-24 01:XX:XX toooooooby/yazawa#9.1 passed
2014-02-24 01:XX:XX toooooooby/yazawa#9.3 started
2014-02-24 01:XX:XX toooooooby/yazawa#9.2 passed
 :
```

## refs.

* [travis-ci/travis](https://github.com/travis-ci/travis#table-of-contents)
* [Travis-CIのビルドをherokuから繰り返し実行する - Qiita](http://qiita.com/sawanoboly/items/7f275e20fb6a643a3553)


