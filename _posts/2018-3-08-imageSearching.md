---
title: "Image Search Program"
date: 2017-10-01
tags: [OpenMp, Image Processing, C++]
header:
  image: "/images/projectImages/imageSearch.jpg"
excerpt: "OpenMp, Image Processing, C++, High Performance Computing, CSE443"
# enabling math equations rendering in markdown
mathjax: "true"
---

## Problem:
Develop a simple image search program, i.e., simple algorithmic implmentation, moving
the mask image row-by-row and column-by-column from left-to-right and top-to-bottom.
Each matched image (.png format in [red, green, blue, alpha]) region in the larger
image would be surrounded with a red box.
![Image Search Example]({{ "/images/projectImages/imgSearchExample.png" | absolute_url }})
[Detailed Project/HW info](https://github.com/kaiLiGit/High_Performance_Computing/blob/master/Homework%237/Homework7.pdf)

## Goal:
The emphasis lies in parallelism (OpenMP) that is to divide up this simple time-consuming algorithmic
approach to a computing cluster (Red Hawk cluster, used at Miami University in my case) to
speed up the image search processing.

* [OpenMP](https://www.openmp.org/):
  > The OpenMP API supports multi-platform shared-memory parallel programming in C/C++.
  > The OpenMP API defines a portable, scalable model with a simple and flexible interface
  > for developing parallel applications on platforms from the desktop to the supercomputer.


## Ideas
The parallelizing strategy boils down to understanding how to allocate individual tasks (or the
number of images / region matches) each thread has to do in the original pictures.
* Two nested for-loops are used to iterate the original image and a region of the original image
  is "cropped" as large as mask image, and the cropped region is moved one pixel at a time row-by-row
  and column-by-column manner whenever the inner for-loop is executing, this we could visualized as one thread may be
  responsible one or more of these column iterations in the inner for-loop at a particular column.
> Depending on the number of threads, each thread may be assigned to different number of rows of
> iterations moving the cropped images column by column in that row. In this case, OpenMP for
> directive will implicitly deal with the intricacies of allocating number of rows of pixels to the
> thread to move the cropped image column by column. OpenMP `for` directive will also take care of the
> index bounds accordingly while allocating the number of rows or columns to each thread.
> Since the cropped region and mask image are always the same or constant during the iterations of
> the beginning two nested for-loops when used to calculate background averages and same shade matching,
> we would just leave them as is. However, the matching pixel regions need to be stored in a list
> and such list is shared data among all the threads, therefore we would create critical sections for
> the list whenever it is being accessed or modified.

___
## Implementation
:point_right: [ImageSearch.cpp solution](https://github.com/kaiLiGit/High_Performance_Computing/blob/master/Homework%237/mysol/lik7_ImageSearch.cpp)

:point_right: [color.cpp](https://github.com/kaiLiGit/High_Performance_Computing/blob/master/Homework%237/mysol/Color.cpp)

:point_right: [ImageProcess.cpp](https://github.com/kaiLiGit/High_Performance_Computing/blob/master/Homework%237/mysol/ImageProcess.cpp)

:point_right: [My Program Report after functional testing](https://github.com/kaiLiGit/High_Performance_Computing/blob/master/Homework%237/mysol/lik7_HW7_Report.pdf)
