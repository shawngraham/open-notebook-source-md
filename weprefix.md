[[
title: install to folder webprefix
tags: [setup]
]]

File ticket with [nullism](https://github.com/nullism/pykwiki/issues/13#issuecomment-146304421) about installing pykwiki in folders, rather than root. He writes:

>Oh! I should also ask what the web_prefix setting is. In this case, it should be set to /dry-run-pykwiki (no trailing slash). The base_url should not need to include a web_prefix (if it only works with it, then I need to fix something, and I apologize if that's the case).

>So, to recap:

    :::ini
    site:
        ....
        base_url: "http://shawngraham.github.io"
        web_prefix: "/dry-run-pykwiki"
