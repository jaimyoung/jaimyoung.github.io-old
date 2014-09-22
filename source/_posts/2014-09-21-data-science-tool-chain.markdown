---
layout: post
title: "Data Science Tool Chain (DSTC)"
date: 2014-09-21 20:12:04 -0700
comments: true
categories: dstc
---

Data science tool chain

1. Bare basic
    1. OSX / Linux. 
    1. SSH. ssh-copy-id.
    1. Bash / zsh. Dotfiles management.
    1. Git. Bitbucket / Github.
    1. Git Pages.
1. RStudio. 
    1. [Google's R style guide](https://google-styleguide.googlecode.com/svn/trunk/Rguide.xml)
    1. [Hadley Wickham R style guide](http://r-pkgs.had.co.nz/style.html)
1. Sublime text editor 
1. Python
    1. Easy route: [Anaconda distribution](http://continuum.io/downloads) with entire [SciPy](http://www.scipy.org/) stack
    1. Style guide. pylint.
        1. [Google's Python style guide](https://google-styleguide.googlecode.com/svn/trunk/pyguide.html)
1. Machine learning / classification / regression
    1. "Elements of Statistical Learning"
    1. Lasso
    1. Lasso w/ large data. 
    1. Random forest. 
    1. Best practices. 
    1. ROC. 
7. Visualize best practice.
    1. Ggplot. Plyr.
7. Feature reduction. 
    1. Principal component
    1. SVD
1. VW or [Vowpal Wabbit](https://github.com/JohnLangford/vowpal_wabbit/wiki)
1. SQL
1. Hadoop MapReduce
    1. AWS EMR
1. [Reproduciblile and collaborative data science](https://www.google.com/search?q=Reproducible+and+Collaborative+Data+Science&oq=Reproducible+and+Collaborative+Data+Science&aqs=chrome..69i57j69i61.407j0j4&sourceid=chrome&es_sm=91&ie=UTF-8).
    1. [The Berkeley Science Review](http://berkeleysciencereview.com/reproducible-collaborative-data-science/), 
    1. ["STAT 157" topics](https://github.com/stat157/fall-2013/blob/master/topic-sketch.md). 



### On style guide and pylint

> Always code as if the guy who ends up maintaining your code will be a violent psychopath who knows where you live. 
<cite>Quoted by Damin Conway in [Perl Best Practices](http://stackoverflow.com/questions/876089/who-wrote-this-programing-saying-always-code-as-if-the-guy-who-ends-up-maintai)</cite>

I found basic pylint to be a bit too aggressive.

``` bash
    $ cat ~/.pylintrc 
    [MESSAGES CONTROL]
    disable=W0403,R0904
    [BASIC]
    # Regular expression which should only match correct variable names
    # variable-rgx=[a-z_][a-z0-9_]{2,30}$
    variable-rgx=[a-z_][a-z0-9_]{0,30}$
```
