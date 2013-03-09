---
date: '2010-02-05 14:31:22'
layout: page
slug: useful-regex
status: publish
title: Useful Regex & Bash
wordpress_id: '319'
comments: true
---

A collection of useful regular expressions I use or I've used during my coding life. They are written using Perl notation.

**CSS : find all the the last rules not terminating with a semi-colon and put one:**
``` bash
s/(\w|\d)(?!;)(\s*|\n)(})/$1;$2$3/g
```

**CSS: find a specific class in your html files:**
``` bash
/class=(\"|\')(\w\s+)*(YourCssClassHere)(\s+\w)*(\"|\')/
```
OR better (using the boundaries)
``` bash
/class=[\"\'][a-zA-Z_\s\-]*?\bYourCssClassHere\b[a-zA-Z_\s\-]*[\"\']/
```
OR (using the boundaries and including the non alphanumeric chars)
``` bash
/class=[\"\'][^\"\']*?\bYourCssClassHere\b[^\"\']*[\"\']/
```
``` bash
/class=\"[^\"]*\bclass\b.*?\"/
```

**PHP: find a list of files that use the htmlentities function but do not include the file functions.php:**
``` bash
ack-grep "\bhtmlentities\b" --type php -l | xargs -I{} ack-grep -c "functions\.php" {} | grep :0 | awk '{split($0,a,":");print a[1]}'
```
