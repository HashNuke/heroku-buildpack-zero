# Heroku Buildpack Zero (for static sites)

My attempt at writing the smallest buildpack. The goal was to stay within the 150 chars limit. The whole buildpack is 112 characters. And it [fits in a tweet](https://twitter.com/HashNuke/status/454238654446043136).

I also [tweeted](https://twitter.com/HashNuke/status/454239536642400257) about it.

```
$ wc -m bin/*
       0 bin/compile
      21 bin/detect
      91 bin/release
     112 total
```

This uses a single threaded web server. I'm trying very hard to crack a joke. Please do not host anything serious with this buildpack :)


## Usage

#### Create a Heroku app with this buildpack

```
heroku create --buildpack "https://github.com/HashNuke/heroku-buildpack-zero.git"
```

#### Set the buildpack of an existing Heroku app

```
heroku config:add BUILDPACK_URL="https://github.com/HashNuke/heroku-buildpack-zero.git"
```


## Notes

#### Other stuff I tried to do to fit in 150 chars

I wrote the following, which writes a buildpack on your local workstation (creating a repo for the buildpack was left to the user). But it was 152 chars. 2 extra.
  
```
mkdir bin;cd bin;echo 'echo 0'>detect;touch compile;printf -- "printf -- '---\\ndefault_process_types:\\n  web:python -m SimpleHTTPServer \\$PORT'">release
```
