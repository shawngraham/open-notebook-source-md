[[
title: Fixing jupyter to run r
tags: [jupyter, setup]
]]


`bash
install_name_tool -change /Users/shawngraham/miniconda3/lib/libzmq.4.dylib /Users/shawngraham/miniconda3/lib/libzmq.5.dylib /Users/shawngraham/miniconda3/lib/R/library/rzmq/libs/rzmq.so
`