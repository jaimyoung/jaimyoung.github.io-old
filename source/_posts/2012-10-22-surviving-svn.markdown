---
layout: post
title: "Surviving SVN"
date: 2012-10-22T16:01:00-07:00
categories:
 - unix
 - toolbox
---

Philosophy: tree organization and life cycle

Below is the typical directory structure. Numbers here mean the typical execution order in the lifecycle of the product. See the section in the official doc or another " practical take". 


    project-name
        trunk : (1) the latest and greatest. Keep working on this all the while (2)-(9) are happening.
            branches
                1.0 : (2) copied from trunk when the 1.0 release is planned (3) test (4) release (6) keep on maintain for bug fixes [merged to/from the trunk] (7) released when enough bug fixes are accumulated ... 
                2.0: (10) copied from trunk whn the 2.0 release is planned .. repeat.
            tag
                1.0.0 (5) tagged when released
                1.0.1 (8) tagged at the time of the bug fix release


Minimal commands

    # start developing
    svn checkout svn+ssh://username@servername/repos/project-name/trunk

    # daily cycle
    svn update
    svn commit -m '

Slightly advanced commands

    # weekly cycle (if working on separate branch)
    svn merge ^/trunk


    # creating branch / tag
    svn copy svn+ssh://username@servername/repos/project-name/trunk \
        svn+ssh://username@servername/repos/project-name/branches/1.0

    # comparing two branches
    # (many modern editors syntax highlight *.diff files)

    svn diff  ^/trunk  ^/branches/1.0 > trunk-vs-1.0.diff

Defensive commands

    # bailing out
    # svn revert xxx or more transparently:
    rm xxx; svn update xxx


    # rolling back to a previous revision
    svn merge -r HEAD:23340 xxx


    svn commit -m 'Rolled back to r 23340'

