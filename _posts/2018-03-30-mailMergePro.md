---
title: "Mail Merge Program"
date: 2017-11-01
tags: [Python, C-sharp, script-language, regular-expression]
header:
  image: "/images/projectImages/mailmerge.jpg"
excerpt: "Python, C#, script-language, regular-expression, CSE465"
# enabling math equations rendering in markdown
# mathjax: "true"
---
## Problem:
Given some *.tsv* files and *.tmp*, where *.tsv* file is tab-separated with values populated for each attribute and *.tmp* is a form letter which has embedded code to be replaced by each corresponding value of the attribute for each mail recipient.

**a.tsv** instance:
![tsv Example]({{ "/images/projectImages/tsvFile.png" | absolute_url }})

**a.tmp** instance:
![Image Search Example]({{ "/images/projectImages/tmpFile.png" | absolute_url }})

[More info on mail-merge program](https://github.com/kaiLiGit/Comparative-Language/tree/master/hw4_c%23_n_python)

___

## Goals:
The goal of this program is to compare the script language features between Python and C#. Regular expression, data structures (LIST and Dictionary), pass-by-reference, dynamic-type in Python, and auto-type in C# are features being explored in this program.
___

## Ideas:
1. Read both *.tsv* and *.tmp* files line by line.
2. Loop through *.tsv* files attributes into an array or a list.
3. Figure out regular expression pattern in *.tmp* file.
4. Substitute each embedded code bracket, begins with `<<` and ends with `>>`, in *.tmp* and write to a string.
5. Write each substituted embedded code bracket to a new file.

___

## Implementation:
:point_right: [My Python code implementation](https://github.com/kaiLiGit/Comparative-Language/blob/master/hw4_c%23_n_python/hw4.py)

:point_right: [My C# code implementation](https://github.com/kaiLiGit/Comparative-Language/blob/master/hw4_c%23_n_python/hw4.py)
