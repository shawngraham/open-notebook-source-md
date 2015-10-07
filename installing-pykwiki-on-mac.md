[[
title: Installing and using Pykwiki on a Mac machine.
tags: [mac, setup]
]]
[TOC]

### Installing Pykwiki

Getting set up on a mac is very easy: follow the instructions at [PykWiki](http://pykwiki.nullism.com/getting-started.html)

### Publish online

To get this site live on the internet, open your github desktop client. Click on the + button to `Add` a repository. Select the path to your docroot folder. Commit all changes (remember to make a commit message), then `publish` (the next time you want to put your changes online, it'll be 'sync'). Github will ask you what you want to call this repository online. 

> IMPORTANT: The repository has to be 'yourusername.github.io'. 

So, just to be clear: you are creating a repository in your github account, that has the name of your associated github.io page:

`http://github.com/shawngraham/shawngraham.github.io` is my repository, and it serves its pages online at `shawngraham.github.io`

Congratulations! Anytime you rebuild your suite with the cache command,
commit and sync to github, and make sure you merge your changes onto the
gh-pages branch too.

> If you have your own server, create a subdomain via your cpanel, and use FTP to copy everything from docroot to that subdomain. At the current moment, it doesn't work when you try to serve it from a folder, ie http://example.com/notebook. So you want: http://notebook.example.com
> 