---
layout: post
title: Diagramming Part 2
description: "Diagramming function calls"
modified: 2015-07-06
category: diagramming
tags: [diagramming, javascript]
imagefeature: coder.jpg
comments: true
featured: true
share: true
---

# Function Calls
When we define functions, the function itself is stored in the frame in which it is defined. We
don't need to know anything about what goes on inside the function until it is called.

As mentioned in the first diagramming blog post, new frames are created when functions are *called*. 
As the function call is executed, local variables are stored within the function call's frame, but
everything else works the same. If
the function references any variables that are not within its frame, it looks to the frame in
which it was defined because Javascript is statically scoped. Another thing to note: data that is
returned is passed up, back to the frame in which the function was called. From there, the data can
be stored in a variable, manipulated, ignored, etc. To see an example of this, step
through the diagramming below.

<div align="center"><iframe width="800" height="500" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=var+str+%3D+%22static%22%0Afunction+f(%29%7B%0A++++return+str%3B%0A%7D%0Afunction+g(str%29%7B%0A++++return+f(%29%3B%0A%7D%0Avar+result+%3D+g(%22dynamic%22%29%3B&origin=opt-frontend.js&cumulative=false&heapPrimitives=false&textReferences=false&py=js&rawInputLstJSON=%5B%5D&curInstr=0&codeDivWidth=350&codeDivHeight=400"> </iframe></div>

