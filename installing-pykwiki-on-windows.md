[[
title: Installing and using Pykwiki on a windows machine.
tags: [windows, setup]
]]
[TOC]


It's easy to use once it's installed; installing can take a little bit of time.

## Install Python 
+ download and install [python 2.7.10](https://www.python.org/downloads/) 
+ download ez_setup.py script (by
right-clicking and selecting 'save as'
[https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py](https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py) 
+ open the command line prompt, and navigate to where you downloaded
(alternatively, use windows explorer to find that folder, then
shift-rightclick on the folder and select 'open command prompt here'.

+ type: `python ez_setup.py`

When the smokes clears, download the get-pip.py script:
[https://raw.github.com/pypa/pip/master/contrib/get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py)

+ Back at the command prompt, type: `python get-pip.py`

Once that's finished go to your python scripts directory using the CD
command at the command prompt `c:\python27\tools\scripts` is where you need to be.

+ type: `win_add2path.py`

This command tells your machine where to look for the commands when you
type them. (This might strictly speaking not be necessary, but it's useful.)

## Install Pykwiki
Now, go back to your user directory, ie `c:\users\yourname` and let's
install pykwiki!

+type: `pip install pykwiki`

## Building a site
When that's finished, let's make a new directory to hold everything
(and every site) we generate. Navigate to your `c:\` folder. In what
we're going to do next, having spaces in for instance your username ie
`\users\Shawn Graham\ ` is going to break things. So we have to go up a
level above users (unless your username has no spaces, in which case
you're fine)

+ type: 
`mkdir pykwikiprojects`

`cd pykwikiprojects`

Now, open a new command window and go back to `C:\Python27\Scripts` .
You're going to run the site generation commands from this location, but
apply them to the folder you made above. Type:

`python pykwiki -b c:\pykwikiprojects\ new website1`

> (if you have no spaces in your username, and wanted to work from that folder, the `-b` flag would look like this: `-b c:\users\myusernamewithoutspaces\pykwikiprojects\ ` )

The `-b` flag tells pykwiki where to do all the work, and you feed it the
path to where you're working. 'new' says build a new site, and call it 'website1'

In your other command window, you now have a website1 subdirectory
inside the pykwikiprojects folder. Inside `website1` there is a folder
called `source`. That's where you save all your markdown documents. You
have another folder called `docroot`. That's where your generated
website will live. Go make a couple of markdown documents (remember, in
a text editor, save as with .md file extension at the end). In your
command window at `c:\python27\scripts`, let's get the site updated:

type: `python pykwiki -b c:\pykwikiprojects\website1\ cache`

`Cache` is the command that tells pykwiki to update the site at that location.The screen will fill with data as it does its work. Let's go see what it
did. Navigate to `c:\pykwikiprojects\website1\docroot` using the cd
command. Then, we're going to tell the computer to serve up all these
files as if it were a webserver. Type:

`python -m SimpleHTTPServer 5000`

Now, in your browser, put this in the address bar: `localhost:5000`

(When you want to quit running the simplehttpserver command, go back to
that command window and hit `ctrl+c` for 'cancel'.)

And your site is running! After this, anytime you want to update your
site, you need to make sure of a couple of things: 

+ no spaces in filenames. 

+ run the pykwiki command from the command line at the `c:\python27\scripts` folder 

+ use the -b flag to always be pointing to your project files (otherwise it will build everything in the `python27\scripts` folder.

+ Once the site is first built, you only need to use the cache command to rebuild the site.

### Publish online

To get this site live on the internet, right-click in the docroot folder
in windows explorer, and select `git init here`. Then, open your github
desktop client. Click on the + button to `Add` a repository. Select the
path to your docroot folder. Commit all changes (remember to make a
commit message), then `publish` (the next time you want to put your
changes online, it'll be 'sync'). Github will ask you what you want to
call this repository online. 

> IMPORTANT: The repository has to be 'yourusername.github.io'. 

So, just to be clear: you are creating a repository in your github account, that has the name of your associated github.io page:

`http://github.com/shawngraham/shawngraham.github.io` is my repository, and it serves its pages online at `shawngraham.github.io`

Congratulations! Anytime you rebuild your suite with the cache command,
commit and sync to github, and make sure you merge your changes onto the
gh-pages branch too.

> If you have your own server, create a subdomain via your cpanel, and use FTP to copy everything from docroot to that subdomain. At the current moment, it doesn't work when you try to serve it from a folder, ie http://example.com/notebook. So you want: http://notebook.example.com
> 
