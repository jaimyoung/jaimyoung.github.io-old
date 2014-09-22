---
layout: post
title: "Surviving date-time, POSIX, unix timestamp... in R, Oracle, MySQL, perl"
date: 2013-01-12T16:16:00-08:00
categories: timestamp utc tips work-in-progress
---

Timezone / timestamps are easy to mess up. 
It helps us in the long run
to have a solid conceptual framework 
by reading about, among others:
[Timezone / UTC / GMT](http://en.wikipedia.org/wiki/Coordinated_Universal_Time),
[Unix epoch / timestamp](http://en.wikipedia.org/wiki/Unix_time),
[ISO 8601](https://en.wikipedia.org/wiki/ISO_8601),
and of course an [XKCD take on this](http://xkcd.com/1179/).

Essentially, most tasks are juggling between a few different entities:

1. **Unix timestamp**: Good.
1. **String with time zone**: Good. e.g. "2013-06-24T10:21:11Z"
1. **String without time zone**: Bad, bad, bad
    * **String with assumed UTC time zone**
    * **String with assumed non-UTC time zone**

## Parsing and formating
### R

Remember strptime is STRing to Posix Time class:


``` r
    # when the string is in "standard" format:
    strftime(as.POSIXlt('2009-12-25 01:23:45'),format='%Y-%m-%d %H:%M:%S')
    # when the string is in non-standard format:
    strftime(as.POSIXlt('2009-12-25 01:23:45'),format='%Y-%m-%d %H:%M:%S')

    # TBD for unix timestamp

    # Date to R date
    as.POSIXlt('2012-01-02T18:27:44.0000000',
    + format='%Y-%m-%dT%H:%M:%S.0000000', tz = 'GMT')

    # R date to unix timestamp. This is simple.
    as.numeric( R date)
    e.g. as.numeric(as.POSIXlt('2012-01-02T18:27:44.0000000',
    + format='%Y-%m-%dT%H:%M:%S.0000000', tz = 'GMT'))

```



### SQL

``` sql
    -- Oracle variant
    select to_char( to_date('yyyy-mm-dd hh24:mi:ss', '2009-12-25 01:23:45'), 'mm/dd/yyyy hh24:mi:ss')
    from dual;

    -- MySQL variant
    SELECT DATE_FORMAT(xxx,'%Y-%m');


    -- PostgreSQL variant
    -- TBD
```

### Perl

``` perl
    use POSIX;
    my $date = POSIX::strftime('%Y-%m-%d', # '%Y-%m-%d %H:00:00',
              gmtime($timestamp));
```

### Java

Save yourself trouble. Use [Joda Time](http://www.joda.org/joda-time/)


## Iterate over days and months
Another imortant 


``` bash
    # TBA
```

``` python
    # TBA
```

``` r
    # TBA
````
