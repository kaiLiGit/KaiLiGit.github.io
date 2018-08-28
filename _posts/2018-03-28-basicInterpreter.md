---
title: "Interpreter Program"
date: 2017-11-01
tags: [Interpreter Implementation, Java]
header:
  image: "/images/projectImages/basicinterpreter.jpg"
excerpt: "Interpreter Implementation, Java, CSE465"
# enabling math equations rendering in markdown
mathjax: "true"
---

## Problem:
Given a *Z+-*, a made-up language, translate and execute a sequence of instructions
written in such language using a high-level language. I picked Java in for this program. Here one example of *Z+-* program text file.
![Image Search Example]({{ "/images/projectImages/zplusminusEx.png" | absolute_url }})
:point_right: [More `.zpm` input files listed in repo](https://github.com/kaiLiGit/Comparative-Language/tree/master/Homework_1)

___

## Goal:
Translate and Execute *Z+-* using a high-level language.

___

## Ideas:
1. Read *Z+-* text files (.zpm) line by line.
2. Use a dictionary `<String, int>` to keep track of variables declaration and values.
3. Be aware to assumptions made towards variables type and values.
4. Throw exceptions or show messages when erroneous syntax encountered.
5. Recursively process `for-loop` statements.
6. [More information on ideas](https://github.com/kaiLiGit/Comparative-Language/blob/master/Homework_1/README.md)

___

## Implementation:  
:point_right: [See my implementation, Java](https://github.com/kaiLiGit/Comparative-Language/blob/master/Homework_1/MyProgram.java)
