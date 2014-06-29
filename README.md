# GoJekyll

## Intro

This is a simple Jekyll bootsrap package.
It is widely inspired from JekyllBootstrap and Octopress. Although i really found these two projects are really neat, they seemed still a bit complicated to me. So i decided to build my own version.

GoJekyll does not nearly have all the fancy stuff you'd exepct from the two i mentionned above. It's only simple jekyll pre-packaged with:

- Compass / Sass
- Twitter Bootstrap
- A custom _config.yml for fast and useful configuration
- Redcarpet2 plugin to enable use of **Github Flavored Syntaxt Highlighting** and **fenced code blocks**
- A `Rakefile` to spare boring tasks (create pages and posts, i.e `compass watch` and `jekyll --server`)

## How to install / use

Simply clone this repo

    $ git clone git://github.com/tobalsan/gojekyll.git myblog

If it's the first time you're going to use Jekyll, then you should make sure that:
  - you are using **Ruby > 1.9.3**
  - you installed the Jekyll gem: `gem install Jekyll` (you might have to run `gem update --system` first)
  - you have the Compass gem: `gem install compass`

GoJekyll also uses [Bootstrap 3](http://getbootstrap.com/) with Compass, so you have to install the [bootstrap-sass](https://github.com/twbs/bootstrap-sass) gem: `gem install bootstrap-sass` .
(do NOT run `compass install bootstrap` like it's mentionned in the bootstrap-sass doc though, as it's been taken care of already).

From there, you're all set to go. Simple tasks are as following:

### Create a post

Same as Jekyllbootstrap

    $ rake post title="My awesome post"

### Create a page

Same as post:

    $ rake page title="My wonderful page"

### Launch Jekyll preview server and compass watch

    $ rake watch

This will launch both `compass watch` to check for any css modification, and `jekyll build && jekyll serve --watch` so you can preview your change at `http://localhost:4000` while having Jekyll watch for anyc change you make in your source code.

## Deployment

The static site is generated in the `web` folder. This folder is ignored by git, so to deploy, simply `cd` into the web directory, and do your stuff here. For example, if you plan to deploy with Git:

    $ cd web/
    $ git init
    $ git remote add origin git@github.com:myusername/myusername.github.com.git
    $ git add .
    $ git commit
    // ..etc