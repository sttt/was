#Websocket Application Server (WAS) using node JS and PHP#

WAS is a webserver with websocket and a mature scripting language.
In this case PHP, running on linux. With a database of your choice.

Install it, run the server and browse the example application.
This example is intended for a small stand alone web application. 

The nice part of this is that all can be served on  port 80 or 443. 
You don't need to run two servers.

This stack consists of:

* node.js: An event-based experimental server written in JavaScript and using googles V8 engine.
* express module: HTML static file server module for node
* WS websocket module for node
* PHP (so far. You can adapt it to a number of mature scripting language that can be run as CGI)
* Add a database of your choice.  

Tested on Wheezy linux as used on the Raspberry PI, which is a Debian warranty. You can easily adapt it to other platforms. 

##Installation##
Install node JS on your system  
There are several ways to do it:  
On Derbian/Ubuntu:  

    $ sudo apt-get install npm php5-cgi

Make sure you get a fairly recent version for your distribution. At least ver 0.10.X
Test with:

    $node -v

Create a project directory.
Node JS contains the nice node package manager npm. Use it to install 3 modules: 

    $ mkdir yourdir
    $ cd yourdir
    $ npm install express ws ini

Get the WAS application:  

    $ wget https://github.com/codemuncky/was.git

Run the server:  

    $ node server.js

Use a browser to access the server on port 8080 eg. localhost:8080  

Change settings in node-was.conf


##PHP##

PHP support is achieved using php-cgi and by transfering request data to a script called PHP-burner, that presents the appropriate superglobals to make it look much like its running in an Apache module.

##Status##

This is Proof of concept. 
* There will be issues it you try to make it a production platform as is.
* If you want to run large off the shelf applications there will be issues as well.
* There are both security and performance issues.
* If this project turn out to be useful and people wish to join it, all that will eventually be ironed out
