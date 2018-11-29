---
title: "article 000: contributing"
date: 2018-11-29
draft: false
---

the objective of this article is to enable us "contributors" to contribute
to The Ordnung (that is, this document tree).

currently this article is all "technical", written as if it's addressing
an experienced developer.

at writing this document will certainly be incomplete most conspicuously
in its lack of documenting how to push out changes to The Ordnung.

mainly we don't have a good workflow for how to anyone may publish
changes (wiki-like), but we can burn that bridge later.




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
version schmersion.



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
are annoying.)



### start out by copy-pasting all the config from the theme's example

(this section is here for posterity. don't do this on an existing The Ordnung.)

making sure you're still in the right directory (just inside "xx"),

```sh
cp themes/min_night/exampleSite/config.toml config.toml
```
note the above doesn't get us where we need to be, but
it's a step towards that.

that's it! (for now)




## editing markdown

in addition to what we propose here, please try to follow whatever existing
conventions are apparenly at play in any existing documents you edit.
our main guidelines (in descending order of importance) are:

  1. no trailing whitespace on any line.

  1. do not exceed 79 characters on a line.
     (the 80th caracter is one too many.)
     we can except fixed-width sections (like for code) and ASCII art and the
     like, but even then it's bad to go too wide.
     explaining why is out of scope, but there are at least two reasons.
     long url's etc are excepted.

  1. four blank lines before each non-first major section. ("major sections"
     are the ones whose headers use two octothorpes. the first section of
     a document doesn't need this many.)

  1. three blank lines before each sub-major section (the ones with three
     octothorpes).

  1. the last line of a file should have content on it. (don't end files
     with a blank line.)




## writing git commit messages

we have adopted [the same guidelines][hugo2] that hugo uses, mixed in
with some OCD of our own:

  - "each commit message should have a title/subject in imperative mood
    starting with a capital letter and no trailing period" (see reference).

  - the first line of the commit message is ideally 50 chars or less.
    commit messages whose first line is wider than 79 chars may be rejected.

  - the first line of the commit message and any subsequent lines in it must
    be separated by exactly one blank line.

  - commit messages longer than one line are great, but if they are the result
    of a squash etc, edit the message so it makes a coherent whole instead of
    just a series of other messages concatenated to each other.




[hugo]: http://gohugo.io
[hugo2]: https://github.com/gohugoio/hugo/blob/master/CONTRIBUTING.md#git-commit-message-guidelines
