---
layout: post
title: "Download a particular file/directory from github"
description: "Download a single folder or directory from a GitHub repo"
comments: true
keywords: "github,git,svn"
---
This is a quick note regarding downloading a single folder or directory from a GitHub repository.
### Download a particular file/directory from git without all extra git stuff.

For this we can use a tool call `svn`. Just do `svn export <git-url> `

* Make sure to remove /tree/master/ and add /trunk/ to the url

__Note:__ It is a good practice is to first do `svn ls <git-url>` to see which files and folders will get downloaded, then do `svn export <git-url> ` to download the file/folder.
