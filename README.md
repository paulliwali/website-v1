Website Description
===================
www.pauldeng.co

Personal Website Used to Host Blog, Resume, Projects, etc

Using `node.js` and `express` framework to deploy onto Heroku, `npm` for package management, Twitter's [bootstrap3](http://getbootstrap.com/) to create initial landing page. May extend to custom `html5`/`css` in the future. 

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


## package.json

Heroku uses `package.json` to identify the application as a node.js app. The file contains all the `npm` dependencies which app requires.
```
npm install
```
to install equivalent dependencies on local machine for local debug.


### References
[node.js Heroku Deployment](https://devcenter.heroku.com/articles/nodejs)
[node.js](http://nodejs.org/)
[express](http://expressjs.com/)
[Coursera: Startup Engineering](https://class.coursera.org/startup-001/class/index)


