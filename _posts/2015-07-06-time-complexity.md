---
layout: post
title: Time Complexity
description: "The basics of determining time complexity of algorithms"
modified: 2015-07-06
category: language agnostic
tags: [time complexity, language agnostic]
imagefeature: complexity.png
comments: true
featured: false
share: true
---

# Big-O Notation
Big-O notation is a common way of expressing the time complexity of an algorithm. It provides an
upper bound on the order of growth of an algorithm. We generally use Big-O to convey how much time a program
will take to execute in a worst-case scenario and how that changes with input size. Asymptotics are
essential in comparing the efficiency of algorithms and data structures because they provide a clear
approximation of how things scale.

In general, we find these approximations by counting operations. Operations such as variable
declarations/assignments, comparisons, object accesses, and simple math operations are usually
assumed to take constant time.



If we say "the runtime of algorithmA is O(f(n))", we express that its order of growth is less than or
equal to f(n). Let's say n is the length of the array we pass into algorithmA. If f(n) = n, then the
runtime will at most double if we double the length of the array.
