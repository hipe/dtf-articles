---
title: article 000 - contributing
date: 2018-11-29
draft: false
---



## creating a new or editing an existing hugo site

this section is here in part for posterity so we remember how we created
a new hugo site, and in part to provide the necessary documentation for
contributors to be able to get set up for editing The Ordnung.



### install hugo

..if necessary. use your package manager, or follow the [hugo][hugo] project's
recommended installation steps for your platform (which may very well be to
just use your package manager).

on OS X we think we did something like:

```sh
$ brew install hugo
```


### create a new hugo site

(if you are contributing to the existing Ordnung, skip.)

we did:
```sh
hugo new site xx
```

we got:

```sh
Congratulations! Your new Hugo site is created in /Users/hipe/Projects/DTF/xx.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/, or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```


### install the theme

whether you're creating a new hugo site or contributing to The existing
Ordnung, you'll need to get a theme into the `themes/` directory and
indicate that theme in the `config.toml` file.

we mostly arbitrarily picked this one theme that we already don't like,
but later for that.

(we literally chose the name "xx" above for the directory of our whole
site, but below, substitute whatever name you're using if you're working
from an existing checkout.)


```sh
cd xx/themes
git clone https://github.com/nathancday/min_night
cd ..
```

☝️ this much is necessary once for every new checkout of an The Ordnung.

(we could instead try to use git submodules, but we aren't because they
are annoying.



### start out by copy-pasting all the config from the theme's example

(this section is here for posterity. don't do this on an existing The Ordnung.)

making sure you're still in the right directory (just inside "xx"),

```sh
cp themes/min_night/exampleSite/config.toml config.toml
```
note the above doesn't get us where we need to be, but
it's a step towards that.

that's it! (for now)


[hugo]: http://gohugo.io
