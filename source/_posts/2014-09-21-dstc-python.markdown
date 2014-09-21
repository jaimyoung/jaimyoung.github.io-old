---
layout: post
title: "DSTC: Python"
date: 2014-09-21 01:17:17 -0700
comments: true
categories: dstc python
---

On Mac OSX, I found it easiest to work with 
[Anaconda distribution](http://continuum.io/downloads). 
This includes, among others, the entire stack of 
[SciPy](http://www.scipy.org/) stack.


### Style guide
I like this quote:

> Always code as if the guy who ends up maintaining your code will be a violent psychopath who knows where you live. 
<cite>Quoted by Damin Conway in [Perl Best Practices](http://stackoverflow.com/questions/876089/who-wrote-this-programing-saying-always-code-as-if-the-guy-who-ends-up-maintai)</cite>

Like a programmer who avoids the violent psycopath, 
it benefits researchers greatly in the long run
when they learn to stick to good coding practice.
One of them is of course a style guie.
I found Google's guide to be useful for languages we use primarily:

* [Google's Python style guide](https://google-styleguide.googlecode.com/svn/trunk/pyguide.html)
    * pylint is good but see below is good.
* [Google's R style guide](https://google-styleguide.googlecode.com/svn/trunk/Rguide.xml)
    * [Hadley Wickham R style guide](http://r-pkgs.had.co.nz/style.html)


### pylint
It's a personal and team's choice but default pylint config could be too aggressive.
I found this to be reasonable.

``` bash
    $ cat ~/.pylintrc 
    [MESSAGES CONTROL]
    disable=W0403,R0904
    [BASIC]
    # Regular expression which should only match correct variable names
    # variable-rgx=[a-z_][a-z0-9_]{2,30}$
    variable-rgx=[a-z_][a-z0-9_]{0,30}$
```

This setup will be globally applied to any python.
