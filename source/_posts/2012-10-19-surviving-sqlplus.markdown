---
layout: post
title: "Surviving sqlplus"
date: 2012-10-19T03:20:00-07:00
categories:
 - unix
 - toolbox
---

Starting

    > sqlplus username/passwd@dbname
    SQL> quit

    > sqlplus username/passwd@dbname / @filename


Editing script / buffer

    SQL> define_editor='vi' 
    -- or emacs if you have one


    SQL> edit
    -- edit the buffer


    SQL> run
    -- run the buffer 

    SQL> save filename
    -- saves the buffer to a file (*.SQL); appends a slash at the end (which is important)


    SQL> edit filename
    -- create a file

    SQL> get  filename
    -- get external file into the buffer


    SQL> start filename
    SQL> @filename
    -- batch run of the file 


    SQL> spool filename
    SQL> spool off
    -- start / stop spooling 

    SQL> !os_command
    -- runs shell command


    SQL> / 
    -- run the command and store it in the SQL buffer.
