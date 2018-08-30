---
title: "Finding the Closest Starbucks"
date: 2016-12-01
tags: [nearest-neighbor, k-d tree, Java]
header:
  image: "/images/projectImages/neareststarbucks2.jpg"
excerpt: "nearest-neighbor, k-d tree, Java, data-structure, CSE274"
# enabling math equations rendering in markdown
# mathjax: "true"
---
## Problem:
Given a list of geological points, or locations in longitude and latitude,
find the nearest Starbucks locations to your current location.

---
## Goal:
Using the provided list of rarely changing Starbucks locations (longitudes, latitudes) coordinates. Find and implement a data structure that solves such kind of nearest-neighbor problem.

---
## Ideas:
`StudentStarbucks` is the implmentation class and should support two operations:
1. `void build(StarbucksLocation[] allStarbucks):`
  * read in all Starbucks locations from a csv file. allStarbucks is a reference to an array of `StarbucksLocation` objects.
  * `StarbucksLocation` contains four variables: city (string), address (string), lng (-180, 180), and lat (-90, 90).
  * retrieve data from csv and populate k-d tree data
2. `StarbucksLocation getNearest(double lng, double lat):`
  * traverse k-d tree to find the nearest Starbucks location

---
## Implementation:

:point_right: [Nearest Neighbor Search Pseudocode](https://www.cs.cmu.edu/~ckingsf/bioinfo-lectures/kdtrees.pdf) from CMU.

---

:point_right: [StudentStarbucks.java](https://github.com/kaiLiGit/CSE274Project/tree/master/ClosestStarbucks/src) code in *Finding the Nearest Starbucks* Project GitHub Repo.

___
