NetLogger
=========

A simple DotNet Logger to use with your NET Projects.


Table of Contents
-----------------



License
-------
* [License](#license)
* [Features](#features)
* [Quick Start](#quick-start)
* [Development](#development)



License
-------

This software is licensed under the [Gnu GPL v3] [1].


Features
--------

NetLogger is a easy to use logging tool.
Loggin to a console or file is as hard as coding helloWorld.

NetLogger offers
* 5 loglevels from critical to debug
* built in easy to use colored console output
* built in easy to use file output
* support for multiple outputs with different loglevels
* automatic Timestamping
* simple api for fast integration into existing projects
* easy configuration with xml
* good extensiblity



Quick Start
-----------

To start with NetLogger:
* add the project or dll to your NET project
* import the namespace logger  
  <pre>import logger</pre>
* add a logAction  
  <pre>logger.addLogAction(logger.stdLogAction)</pre>
* log your messages  
  <pre>logger.log(message)</pre>


Now that you know how to start, lets have a look at some important things.
The main concept of NetLogger is to proceed the logging input and output separatly.
You can allways log, but as long as you add a logAction to the logger, nobody will ever see it.
You can add as much log actions as you want. NetLogger contains two types of logActions  
* consoleLogger
* fileLogger

and has a predefined builtIn LogAction which you can access with logger.stdLogAction. 

But you can easiely extend it to fit your needs. Maybe a dataBaseLogger? 
As most loggers, NetLogger makes use of loglevels. 
It supports  
  0. critical  
  1. error  
  2. warn  
  3. log  
  4. debug  

Each logAction is listing to messages with a given loglevel and below.

Lets assume you want to create a logfile for warnings, errors etc.
  <pre>logger.addLogAction(new fileLogger(2,logfile,true)</pre>  



Ok, so far for the logActions.
How to log?
You have two ways to log:  
  1. Use the loglevel with logger.log 
  <pre>logger.log(loglevel, message)</pre>
  2. Use the named methods  
  <pre>logger.critical(message)</pre>
  <pre>logger.err(message)</pre>
  <pre>logger.warn(message)</pre>
  <pre>logger.log(message)</pre>
  <pre>logger.debug(message)</pre>

As you may mentioned, you don't need a instance of logger. 
As everythink is Shared / Static, there is no need of passing the looger around your classes and modules.  


Last but not least. You may want to extend NetLogger to fit your needs.
This can be done in two ways:  
  1. Write your own logAction by implementing the ILogAction Interface
  2. Make use of the api to get the log messages

The code is easy to understand, just have a look.  



Development
-----------

NetLogger is under constant development. It started as a fast coded tool I used in one project.
But as you allways need logging, especialy in the development phase, I started to use it on all my projects
and finally decided to publish it. Your welcome to contribute, fork and use it as you want.
I'm sure there are a lot of better, more powerfull and faster loggers out there, but it was of use for me, so maybe it
will be of use for others too.



[1]: http://www.gnu.org/licenses/gpl-3.0-standalone.html "Gnu General Public License Version 3"
