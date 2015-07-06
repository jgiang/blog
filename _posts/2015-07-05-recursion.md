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

WARNING: This post is a work in progress! It is still pretty convoluted.

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
So we want to call the function within its own body... Seems like the code within the function is
going to be executed multiple times... like the body of the loop in our iterative approach!
Likewise, our function body should be manipulating the data available to it (the input to the
function) to get closer to a result. But where does the recursive call come in?

Here's how it goes: 
The function body should manipulate the input (do what it needs to do with the input) and then hand off a chunk of the problem to a recursive call, which will continue this manipulation/hand-off procedure. Each recursive call needs to return its result so that it can be used in the bigger picture. The function needs
to use the result of the recursive call (the solution to a smaller chunk of the problem) to
solve the whole problem it's facing. Since we count on the recursive call to give us a partial
solution, we call this part our "leap of faith".

So far, the function will do whatever it does until it calls itself,
then the new function call will execute all the code before *its* recursive call... etc. Hopefully
this makes you feel a little uneasy. When will it stop calling itself?!

That's where the base case comes in. Like the loop conditional in the iterative approach, our
base case needs to determine when we have made enough recursive calls. It should handle the simplest
inputs. Since our recursive calls are tackling smaller and smaller problems, the base case should
recognize when we are given the simplest/smallest problem and just return the answer. This will stop
the recursion from going on forever and start the process of piecing together answers as they find
their way up the chain.

####General Recipe for Recursion
1. Base Case(s)
    - handle the simplest inputs

2. Recursive Call(s)
    - call the function on a smaller/simpler input
        - get your input closer to a base case
    - take a "leap of faith"
        - use a recursive call to solve the larger problem

3. Return
    - return the result!
    - you want to be able to use the result of the recursive calls

<div align="center"><iframe width="900" height="400" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=function+factorial(n%29+%7B%0A++++if+(n+%3D%3D%3D+0%29+%7B%0A++++++++return+1%3B%0A++++%7D%0A++++return+n+*+factorial(n-1%29%3B%0A%7D%0A%0Afactorial(3%29%3B&origin=opt-frontend.js&cumulative=false&heapPrimitives=false&textReferences=false&py=js&rawInputLstJSON=%5B%5D&curInstr=0&codeDivWidth=350&codeDivHeight=400"> </iframe></div>
<figcaption>recursive factorial</figcaption>
