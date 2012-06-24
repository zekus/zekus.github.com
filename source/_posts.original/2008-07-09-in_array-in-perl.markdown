---
date: '2008-07-09 12:27:51'
layout: post
slug: in_array-in-perl
status: publish
title: in_array() in Perl?
wordpress_id: '111'
categories:
- Perl
- PHP
tags:
- array
- grep
- in_array
- Perl
- PHP
---

I was looking for this useful function I always use in php and found this simple [article](http://assasiner.wordpress.com/2006/12/03/is-in-array/trackback/).
Basically, the function that permit you to do that is **grep **used in this way:
```
my $string = ‘fin_helm’;
my @array = qw/full_plate manteau boots two_handed_sword fin_helm/;
if(grep $_ eq $string, @array)
{
print “$string is in the array”;
}
```
easy?
