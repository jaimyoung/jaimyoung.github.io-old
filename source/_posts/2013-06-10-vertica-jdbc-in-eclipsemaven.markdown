---
layout: post
title: "Vertica JDBC in Eclipse/Maven"
date: 2013-06-10T18:24:00-07:00
---
#### Problem:
Want to use Vertica JDBC driver in Eclipse/Maven dependency, but Maven central repository doesn’t have it.

#### Solution:

1. Download vertica JDBC driver jar.
1. At the same directory of that jar, run the following similar to what’s described here. (somehow, running it in an different directory didn’t work. Just created that annoying “*.jar.lastUpdated”)

        $ mvn install:install-file -DgroupId=vertica -DartifactId=vertica-jdbc -Dversion=4.0.19 -Dpackaging=jar -Dfile=~/Downloads/vertica/vertica_4.0.19_jdk_5.jar -DgeneratePom=true
1. In Eclipse, Navigate > Show View > Other > Maven Repository
1. Open Local Repositories
1. Rebuild Index

Now it shows up in “Add…” dialog in pom.xml edit. 

Then have fun:

1. http://chimpler.wordpress.com/2013/05/10/installing-and-comparing-mysqlmariadb-mongodb-vertica-hive-and-impala-part-1/
1. http://tomgendron.wordpress.com/tag/connecting-java-to-vertica/
