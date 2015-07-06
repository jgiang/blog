---
layout: post
title: Diagramming Part 1
description: "The basics of diagramming your code"
modified: 2015-07-02
category: diagramming
tags: [diagramming, javascript]
imagefeature: coder.jpg
comments: true
featured: true
share: true
---

# Defining Variables
Knowing what’s going on during runtime is essential to debugging and understanding your code.

A great tool for this is a website called [PythonTutor](http://www.pythontutor.com/visualize.html#mode=edit). The name is a bit deceiving; it is actually compatible with a couple of different programming languages, including JavaScript. Given a snippet of code, PythonTutor will walk you step-by-step through diagramming your program as it runs.

Although this incredibly useful tool exists, it is extremely valuable to be able to diagram on your own. We will use PythonTutor as a starting point to learn the basics of how to structure our diagrams, but the goal is to internalize the process.

Let’s start with a simple snippet of code to get see how variables are declared and initialized.

{% highlight js linenos %}
var num = 0;
var bool = true;
var str = "hello world";
var numArray = [0, 1, 2];
var arrPtr = numArray;
var increment = function() {num += 1};
{% endhighlight %}

### Some rules (Javascript):
* Primitives types (numbers, booleans, strings, and null/undefined) are passed by value
* Everything else (non-primitive data, including functions) is an object and is passed by reference
* All data is stored in frames, starting at the global frame
* New frames are created when functions are called

PythonTutor walks us through this code, showing which line is being executed at each step and how that execution affects the values of variables in our frames.

<div align="center"><iframe width="900" height="350" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=var+num+%3D+0%3B%0Avar+bool+%3D+true%3B%0Avar+str+%3D+%22hello+world%22%3B%0Avar+numArray+%3D+%5B0,+1,+2%5D%3B%0Avar+arrPtr+%3D+numArray%3B%0Avar+increment+%3D+function(%29+%7Bnum+%2B%3D+1%7D%3B&origin=opt-frontend.js&cumulative=false&heapPrimitives=false&textReferences=false&py=js&rawInputLstJSON=%5B%5D&curInstr=0&codeDivWidth=350&codeDivHeight=400"></iframe></div>

<figcaption>click through the steps to get a feel for how data is stored</figcaption>

A separate post about pass-by-value vs pass-by-reference may also be in the near future!
