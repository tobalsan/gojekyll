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

From there, you're all set to go. Simple tasks are as following:

### Create a post

Same as Jekyllbootstrap

    $ rake post title="My awesome post"

### Create a page

    $ rake page name="my-new-page.md"

Notice here, the argument is the file name, as opposed to the post creation where we specify a title. Thus, use a sluggish name (i.e no spaces or fancy characters).

### Launch Jekyll preview server and compass watch

    $ rake watch

This will launch both `compass watch` to check for any css modification, and `jekyll --auto --server` so you can preview your change at `http://localhost:4000` while having Jekyll watch for anyc change you make in your source code.


## Deployment

The static site is generated in the `web` folder. This folder is ignored by git, so to deploy, simply `cd` into the web directory, and do your stuff here. For example, if you plan to deploy with Git:

    $ cd web/
    $ git init
    $ git remote add origin git@github.com:myusername/myusername.github.com.git
    $ git add .
    $ git commit
    // ..etc