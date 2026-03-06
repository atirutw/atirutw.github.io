---
title: Previewing a GH Pages site locally
author: Atirut Wattanamongkol
fediverse_creator: "@Atirut@toot.community"
tags: jekyll github-pages ruby
---

...a.k.a. "why is Ruby package management so damn convoluted?"

And I'm not answering that question, by the way, because I actually asked that.

Now that I've got my own blog site up, being able to preview changes locally without waiting for GitHub's Actions container to spin up quickly became essential. Did I finally do it? Well, yes! I had to jump through quite a few hoops, but it's possible.

If you're looking to start your own GH Pages blog, I hope this will help you get started with the local stuff. **Before we begin, please note that you're out of luck on Ubuntu, because `gem` has permission problems which *will* drive you insane by requiring `sudo` for everything you do. Yes, *everything*, even using `bundle` to install packages.** I do not know if other distros have this problem, but Fedora works fine for me.

Let's start the journey, shall we?

## The basics

First off, install `gem` and some other stuff...
```bash
sudo dnf install rubygems ruby-devel make gcc g++
```
See those development packages? They will be important for installing packages via `gem` later on, and `rubygems` doesn't have them as a dependency for some reason.

Then, install `bundler` and `jekyll`
```bash
gem install bundler jekyll
```

## Creating/Importing
### Creating a new site
If you're not importing an existing site already hosted on GitHub Pages, you can follow [the official quickstart guide](https://jekyllrb.com/docs/) and continue on from there. 

### Importing an existing GH Pages site

By default, GitHub actually allow you to omit *a lot* of files that would be necessary for previewing files locally, the most important one being `Gemfile`. So, run `jekyll new <insert site name here>`, navigate into the generated directory, rip out `Gemfile` (and optionally, `.gitignore`) into your actual site, and disgard the rest of the generated directory into your recycle bin.

## Prepping for GH Pages
Open up `Gemfile` in whatever text editor you use (I won't judge), and...
- Remove or comment out the line that says `gem "jekyll", "~> 4.3.3"`. It should be on line 10.
- Uncomment `gem "github-pages", group: :jekyll_plugins`. It should be on line 15.
- Update the installed packages by running `bundle install`.

After all that, install our final secret dependency by running `bundle add webrick`. Now, you should be able to run `bundle exec jekyll serve`, click on the link it spits out, and start working on your site locally.
