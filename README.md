Website Description
===================

Personal Website Used to Host Blog, Resume, Projects, etc

Using `node.js` and `express` framework to deploy onto Heroku, `npm` for package management, 

Files
=====

## .gitignore

Used by git to ignore files.
In this case, `node modules` are ignored.


## Procfile

A text file used by Heroku to start specific web dynos. 
In this case `node` is initiated to run the `web.js` script

## web.js

The express() app which calls `index.html` and opens port 8080 for local debug


