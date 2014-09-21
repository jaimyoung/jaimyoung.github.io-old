---
layout: post
title: "Dive into Jekyll/Octopress + Github Pages"
date: 2014-09-21 00:50:40 -0700
comments: true
categories: jekyll github octopress
---

I found Google's Blogger to be tiring in writing workflow.
I looked into a few options:

* Blogger (working harder!)
    * Pros: Familar google workflow, most of times; analytics out-of-box.
    * Cons: Slow. Not flexible.
* Wordpress
    * Pros: Popular.
    * Cons: Slow.
* Github (md only), or even Gist?
    * Pros: Markdown is already my friend.
    * Cons: This is not blog.
* Github Pages, via Jekyll
    * Pros: Markdown is already my friend; speed; geek credential.
    * Cons: Initial investment. Too flexible / too many options.
* Github Pages, via Jekyll/Octopress
    * Pros: Markdown is already my friend; speed; geek credential; setup is more automatic than Jekyll only option.
    * Cons: Slightly overweight than Jekyll only.


From a few factors, I chose "Github Pages with Jekyll/Octopress" option,
after trying out a bit with Jekyll (no Octopress) option.

So far, so good.

## TODO:

1. Turn on Discus Comment
1. Turn on Google analytics
1. Won't do. ~~Maybe make letters smaller?~~
1. Done. ~~Migrating old blogger.~~
    1. To-do. Will follow [http://import.jekyllrb.com/docs/blogger/](http://import.jekyllrb.com/docs/blogger/)
    1. Actually, followed [this gist](https://gist.github.com/baldowl/1578928). 
    1. Still, need to choose what to keep (none?)

## Caveats
If using oh-my-zsh, rake gives zsh: no matches found error all the time. Add this to .zsh

    alias rake='noglob rake'

https://www.linkedin.com/in/statkwon


    rake new_post["Dive into Jekyll/Octopress + Github Pages"] 
    rake new_page[""]
    rake new_page[about]
    rake new_page[super-awesome]
    # creates /source/super-awesome/index.markdown

Workflow

    rake generate   # Generates posts and pages into the public directory
    rake watch      # Watches source/ and sass/ for changes and regenerates
    rake preview    # Watches, and mounts a webserver at http://localhost:4000

Deploy/publish

    rake generate
    rake deploy

## Links

* [http://octopress.org/docs/deploying/github/](http://octopress.org/docs/deploying/github/)
* Tag cloud + category list [https://github.com/tokkonopapa/octopress-tagcloud](https://github.com/tokkonopapa/octopress-tagcloud)
