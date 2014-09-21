---
layout: post
title: "DSTC: Sublime Text Editor"
date: 2014-09-21 01:14:36 -0700
comments: true
categories: 
---

To start, first download sublime text 3. 
Then install a few useful packages:

1. Install package control
2. Install bunch of packages:
    2. sublimelinter
    3. sublimelinter-pylint (see below)
    4. markdown-extended
    5. monokai-extended (and enable it)
    4. git gutter

Default settings work well, but one might want to change the "user" setting 
for handling tabs:

    "translate_tabs_to_spaces": true
    "tab_size": 4,
    "detect_indentation": true,

Syntax specific changes in tab_size is also useful. For *.R for example:

    "tab_size": 4,

### Sublimelinter + pylint + anaconda python on Mac OSX conundrum
Mac OSX Path for python in sublime is messed up by default. 
Default pylint install leads to:

    SublimeLinter: WARNING: no pylint version could be extracted from:
    Traceback (most recent call last):
      File "/usr/local/bin/pylint", line 5, in <module>
        from pkg_resources import load_entry_point
      File "/System/Library/Frameworks/Python.framework/Versions/2.7/Extras/lib/python/pkg_resources.py", line 2603, in <module>
        working_set.require(__requires__)
      File "/System/Library/Frameworks/Python.framework/Versions/2.7/Extras/lib/python/pkg_resources.py", line 666, in require
        needed = self.resolve(parse_requirements(requirements))
      File "/System/Library/Frameworks/Python.framework/Versions/2.7/Extras/lib/python/pkg_resources.py", line 565, in resolve
        raise DistributionNotFound(req)  # XXX put more info here
    pkg_resources.DistributionNotFound: pylint==1.3.1

Add the following to sublimelinter-user:

``` js
{
    "user": {
    ...
        "paths": {
            "linux": [],
            "osx": [
                "/Users/jaimiekwon/anaconda/bin/"
            ],
            "windows": []
        },
        "python_paths": {
            "linux": [],
            "osx": [
                "/Users/jaimiekwon/anaconda/bin/"
            ],
            "windows": []
        },
}
```
