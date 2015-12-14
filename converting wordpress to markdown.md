[[
title: wordpress to markdown
tags: [setup, mac, python, wordpress, md]
]]



Went to https://github.com/mheadd/wp2md

Download the zip (pip install doesn't work)

In the terminal, ```python setup.py install```

Then, where I have the wordpress xml file, ```wp2md paula.xml paulafiles```  makes a folder called paulafiles filled with the wordpress blog posts, converted to md.

I can then drag and drop all of the md files into gitbooks.com at the editor window.