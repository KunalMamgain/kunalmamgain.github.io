---
layout: post
title: "Download a Particular File/Folder from Github"
description: "Download a single folder or directory from a GitHub repo"
comments: true
keywords: "github,git,svn"
---

For this we can use a tool call `svn`. Just do 
```bash 
svn export <git-url-to-file/folder>
```

Make sure to remove /tree/master/ and add /trunk/ to the url

__Note:__ It is a good practice is to first do `svn ls <git-url>` to see which files and folders will get downloaded, then do `svn export <git-url> ` to download the file/folder.
