---
title: "Serialization"
date: 2017-12-01
tags: [C-sharp, Serialization]
header:
  image: "/images/projectImages/Serialization.jpg"
excerpt: "C#, Serialization, CSE465"
# enabling math equations rendering in markdown
mathjax: "true"
---
## Problem:
Develop a `C#` program to serialize/deserialize objects whose classes contain:
  * a default constructor
  * all data members are public and are one of the following primitive types:
    `int` (Int32), `double` (Double), or `Boolean` (Boolean).
Serialization/Deserialization Example:
![serialize Example]({{ "/images/projectImages/serializeEx.png" | absolute_url }})

:point_right: [more reference info](https://github.com/kaiLiGit/Comparative-Language/blob/master/Homework%235/README.md)

___

## Goals:
Not to seek help of any library serialization functions. Learn the inner-working
of serialization and deserialization by using `C#`.

___

## Ideas:
1. For serialization:
  * know structural notion of the object type
  * extract data type name and its value
  * concatenate data type name and its corresponding value to each object of object(s).
2. For deserialization:
  * know primitive data types entail in the object type, int, double, and boolean
  * get the object type and create object if it is primitive (base case)
  * create object from known type
  * simple string manipulation to extract out open and end curly braces
  * deserialize nested objects iteratively until the end curly brace

___

## Implementation:

:point_right: [MySerialize.cs code file](https://github.com/kaiLiGit/Comparative-Language/blob/master/Homework%235/MySerializer.cs)
