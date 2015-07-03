---
layout: post
title: Diagramming Part 1
description: "The basics of diagramming your code"
modified: 2015-07-02
category: diagramming
tags: [diagramming]
imagefeature: coder.jpg
comments: true
featured: true
share: true
---

# Diagramming Your Code: Part 1 Defining Variables
Knowing what’s going on during runtime is essential to debugging and understanding your code.

A great tool for this is a website called [PythonTutor](http://www.pythontutor.com/visualize.html#mode=edit). The name is a bit deceiving; it is actually compatible with a couple of different programming languages, including JavaScript. Given a snippet of code, PythonTutor will walk you step-by-step through diagramming your program as it runs.

Although this incredibly useful tool exists, it is extremely valuable to be able to diagram on your own. We will use PythonTutor as a starting point to learn the basics of how to structure our diagrams, but the goal is to internalize the process.

Let’s start with a simple snippet of code to get see how variables are declared and initialized.

{% highlight js %}
var num = 0;
var bool = true;
var str = "hello world";
var numArray = [0, 1, 2];
var arrPtr = numArray;
var increment = function() {num += 1};
{% endhighlight %}

### Some rules:
* In JavaScript: Primitives types (numbers, booleans, strings, and null/undefined) are passed by value
* In JavaScript: Everything else (non-primitive data, including functions) is an object and is passed by reference
* All data is stored in frames, starting at the global frame
* New frames are created when functions are called

PythonTutor walks us through this code, showing which line is being executed at each step and how that execution affects the values of variables in our frames. The final diagram should look like this:

<img src="{{site.url}}/images/diagramming-1.png">
<figcaption>diagram after all of the code to the left has been executed</figcaption>
The next post will tackle diagramming function calls!

A separate post about pass-by-value vs pass-by-reference may also be in the near future!
