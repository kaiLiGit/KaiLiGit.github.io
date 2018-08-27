---
title: "Web Server Class"
date: 2016-11-20
tags: [server socket, C++]
header:
  image: "/images/projectImages/webServerClass.jpg"
excerpt: "server socket, C++"
# enabling math equations rendering in markdown
mathjax: "true"
---
## Problem:
Implement a basic server class that can serve as a web-server that respond to a *GET* request for a file path.

___
## Goal:
  * Make use of server socket methods from boost library
  * Develop a basic web server to serve text, html, png, and jpeg files

___
## Ideas:
*GET* request received in such format: `GET file HTTP/1.1`
   * *file* is */* should respond with contents of given index.html
   * valid *file* path indicates such file is readable and the server should respond with the *file*'s contents and appropriate HTTP headers & MIME type for the file derived from the *file* name extension. The contents of the file can be sent to client by the server line-by-line.

   | Extension     | MIME type     |
   | ------------- |:-------------:|
   | .html         | text/html     |
   | .png          | image/png     |  
   | .jpg          | image/jpeg    |  
   | .txt          | text/plain    |
   | Default (i.e, in all other cases) | text/plain|

   * In cases of unreadable *file* path, the server program should respond with the following HTTP 404 error response and body. The content length and file name would change based on the appropriate *file* specified in the *GET* request.
   Example:

   ___

   ![alt text](https://github.com/kaiLiGit/kaiLiGit.github.io/blob/master/images/projectImages/unreadblefile.png)
   ___
