---
layout: post
title: Intro to Recursion
description: "The basics of recursive thinking"
modified: 2015-07-05
category: recursion
tags: [recursion]
imagefeature: fractal.png
comments: true
featured: true
share: true
---

# What is a recursive function?
A recursive function is simply a function that calls itself.

If you're not familiar with recursion yet, you have probably been solving your problems
interatively. Luckily, transitioning from iterative thinking to recursive thinking isn't too hard.
We're going to look at code that computes factorials!

##Iterative Approach
Iterative solutions usually require some kind of loop that executes the same code over and over,
changing variables as it goes. The code within the loop manipulates the data so that
each iteration gets us closer to our desired result. The loop conditional determines how many iterations need to be done
in order to get the result we're asking for. Step through this iterative factorial algorithm to see
what happens when we want to calculate 3!.

<div align="center"><iframe width="900" height="400" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=function+factorial+(n%29+%7B%0A++++for+(var+i+%3D+n+-+1%3B+i+%3E+0%3B+i--%29+%7B%0A++++++++n+%3D+n+*+i%3B%0A++++%7D%0A++++return+n%3B%0A%7D%0A%0Afactorial(3%29%3B&origin=opt-frontend.js&cumulative=false&heapPrimitives=false&textReferences=false&py=js&rawInputLstJSON=%5B%5D&curInstr=0&codeDivWidth=350&codeDivHeight=400"></iframe></div>
<figcaption>iterative factorial</figcaption>

Here comes the new stuff. Let's try to work our way from the iterative algorithm to a recursive one.

##Recursive Approach
So we want to call the function within its own body... Seems like the function itself is taking over
the job of the code within the loop. The function will do whatever it does until it calls itself,
then the new function call will execute all the code before its recursive call... etc. Hopefully
this makes you feel a little uneasy. When will it stop calling itself?!

That's where the base case comes in. Like the loop conditional in the iterative approach, our
base case needs to determine when we have made enough recursive calls.

####General Recipe for Recursion
* Base Case(s)
    - handle the simplest inputs
* Recursive Call(s)
    - call the function on a smaller/simpler input
        - get your input closer to a base case
    - take a "leap of faith"
        - use a recursive call to solve the larger problem
* Return
    - return the result!
    - you want to be able to use the result of the recursive calls

<div align="center"><iframe width="900" height="400" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=function+factorial(n%29+%7B%0A++++if+(n+%3D%3D%3D+0%29+%7B%0A++++++++return+1%3B%0A++++%7D%0A++++return+n+*+factorial(n-1%29%3B%0A%7D%0A%0Afactorial(3%29%3B&origin=opt-frontend.js&cumulative=false&heapPrimitives=false&textReferences=false&py=js&rawInputLstJSON=%5B%5D&curInstr=0&codeDivWidth=350&codeDivHeight=400"> </iframe></div>
<figcaption>recursive factorial</figcaption>
