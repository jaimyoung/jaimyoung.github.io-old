---
layout: post
title: "Oracle client on Mac OS X Mountain Lion"
date: 2013-01-23T14:41:00-08:00
---

Again, the challenge is that "there are too many different ways to do this".

    Download all oracle instant client files
        Should download 32 bit files, not 64 bit! 
        They include basic, jdbc, sdk, and sqlplus
    Unzip them all to ./instantclient_10_2 (or some other version)
    Copy them all to /usr/local/oracle/instantclient_10_2
    Add the following in /etc/profile
        export DYLD_LIBRARY_PATH="/usr/local/oracle/instantclient_10_2"
        export SQLPATH="/usr/local/oracle/instantclient_10_2"
        PATH=$PATH:/usr/local/oracle/instantclient_10_2
        export ORACLE_HOME="/Library/Oracle"
        export CLASSPATH="/usr/local/oracle/instantclient_10_2"
    Make /Library/Oracle/network/admin
    Make /Library/Oracle/network/admin/tnsnames.ora and add a few entries there


Some references:

    http://stackoverflow.com/questions/684352/installing-oracle-instantclient-on-mac-os-x-without-setting-environment-variable
    http://digitalsanctum.com/2007/07/26/installing-oracle-instant-client-on-mac-os-x/
    http://www.oracle.com/technetwork/topics/intel-macsoft-096467.html
    https://forums.oracle.com/forums/thread.jspa?threadID=2256568