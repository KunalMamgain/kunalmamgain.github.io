---
layout: post
title: "Useful regex one liners"
description: "List of some useful regex one-liners"
comments: true
keywords: "regex,examples"
---
This is list of some useful regex oneliners that were used by me in past. This list will get appended as I get to know more about other regex expressions.

Here is a quick example of I use these expressions in bash.
```bash
cat <any-file> | grep -Eo '<insert-regex-expression>'
```
* To get all ip address from a file
```
((?:(?:25[0-5]|2[0-4]\d|((1\d{2})|([1-9]?\d)))\.){3}(?:25[0-5]|2[0-4]\d|((1\d{2})|([1-9]?\d))))
```
* To get all links from a file

```
(?:(?:https?|ftp):\/\/)?[\w/\-?=%.]+\.[\w/\-?=%.]+

```
