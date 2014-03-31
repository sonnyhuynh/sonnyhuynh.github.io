---
layout: post
permalink: /coding/ftp-ascii-vs-binary
comments: true

title: FTP - ASCII vs Binary
description: General rule of thumb for deciding which FTP transfer mode to use
date: 2013-10-17 06:06 PM

categories: notes
tags: coding basics ftp

published: true
---

### Which FTP transfer mode should you use to download/upload a file? ASCII or binary?

Here's my general rule of thumb:

- **ASCII:** Anything that can be edited via text editor (e.g. html, css, scripts, text files)

- **Binary:** Everything else (e.g. PDFs, images, music, videos)

### FTP clients typically have an auto-detect mode, so why might you want to know this?

Let's say you're SSH-ed into one machine and want to get a file from another machine. You won't have the luxury of using an FTP client to get that file. You're going to have to use `ftp` via command line, so not knowing which mode to get the file in will result in corrupt files! (Don't worry if you discover your file is corrupt, just get the file again in the other mode!)

> Not familiar with `ftp` via command line and want to learn or refresh your skills? Check out The Geek Stuff's [FTP and SFTP Beginners Guide with 10 Examples](http://www.thegeekstuff.com/2010/06/ftp-sftp-tutorial/)