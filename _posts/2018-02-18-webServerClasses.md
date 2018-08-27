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
HTTP/1.1 404 Not Found
Server: SimpleServer
Content-Length: 47

The following file was not found: data/blah.txt

___

  * Funtional testing
    - run the executable after compilation of the server program
    - make use of `wget` command in Linux environment (wget serves as web-browser to GET data from any valid URL)
    - The `-S` option tells `wget` to print headers sent by the web-browser
    - The `-q` option tells `wget` to be as quiet (not to print additional info)
    - The `-O` option tells `wget` to write the data from the web-server to a given file.

    1. `wget - S "http://ceclnx01.cec.miamioh.edu:Port/Path" -O my_Path 2> my_Path_hdrs.txt`

    2. `diff my_Path Path`

    3. `diff my_Path_hdrs.txt Path_hdrs.txt`

___
Server Class implementation:
:point_right: [Server.cpp](https://github.com/kaiLiGit/CSE278Project/blob/master/Project4/Server.cpp)

Server Class declaration:
:point_right: [Server.h](https://github.com/kaiLiGit/CSE278Project/blob/master/Project4/Server.h)

Main.cpp for testing purpose:
:point_right: [main.cpp](https://github.com/kaiLiGit/CSE278Project/blob/master/Project4/main.cpp)
