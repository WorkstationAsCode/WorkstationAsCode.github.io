# Change Log

## Warning

> :warning: This is my personal change log. I keep for my future me.
> If you are not me, do not waste your time on this page!

## 2021.08.14

### New Gmail account

```txt
Email: workstation.as.code@gmail.com
```

### New Twitter account

Note: username is limited to 15 :disappointed:
```txt
Name: @WorkstationAsC
```

### New GitHub Organization

```txt
Free plan
Name: WorkstationAsCode
Twitter: WorkstationAsC
Location: Switzerland
```

### Create a new repository for GitHub Pages

```txt
Name: WorkstationAsCode.github.io
Description: WorkstationAsCode (WAC)
Public
License: GNU General Public License v3.0
```

### Clone repository

```bash
$ git clone git@github.com:WorkstationAsCode/WorkstationAsCode.github.io.git
```

### Install Jekyll

https://jekyllrb.com/docs/

```bash
$ sudo apt-get install ruby-full build-essential zlib1g-dev
$ export GEM_HOME="$HOME/.gem"
$ gem install jekyll bundler
```

### Create a new Jekyll site

https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll

```bash
$ cd WorkstationAsCode/WorkstationAsCode.github.io
$ ~/.gem/bin/jekyll new --skip-bundle --force .
$ ~/.gem/bin/bundle exec jekyll serve --trace
```

`Commit: Default Jekyll new site`

### Change Jekyll gem version for GitHub Pages

https://pages.github.com/versions/

`Commit: Prepare Jekyll for GitHub Pages`

```bash
$ rm Gemfile.lock
$ ~/.gem/bin/bundle install
$ ~/.gem/bin/bundle exec jekyll serve --trace
```

`Commit: New gem versions resolved by bundle install`

### Revert Jekyll theme and copy only some files locally

`Commit: Add command history`
