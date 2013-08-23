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

## index.html

Utilizes Twitter's [bootstrap3](getbootstrap.com/getting-started/) for stylization as of now. Will incorporate Google Analytics for market reearch.

## Setup:

1. On a clean EC2 instance clone and run [setup](https://www.github.com/paulliwali/setup)
```
sudo apt-get install -y git-core
git clone https://github.com/paulliwali/setup.git
./setup/setup.sh
```

2. Generate a new ssh key and updated it on Github
```
ssh-keygen -t rsa
cat ~/.ssh/id_rsa.pub
```

3. Clone over this [git](https://www.github.com/paulliwali/website)
```
git clone git@github.com:paulliwali/website.git
```

4. Setup git config
```
git config --global user.name $USERNAME
git config --global user.email $EMAIL
```

5. Exit and re-enter the EC2 instance
```
exit
ssh -i  filename.pem ubunutu@ip_address
```

6. Install `npm` dependencies inside the website directory
```
cd website
npm install
```

7. Update Heroku with ssh key, and create the Heroku apps is not previously created
```
heroku login
heroku keys:add
heroku apps:create appname-s --remote staging-heroku
heroku apps:create appname --remote production-heroku
```

8. To add existing Heroku apps to git remotes
```
heroku git:remote -a appname-s -r staging-heroku
heroku git:remote -a appname -r production-heroku
```

9. To push to git and Heroku
```
git push origin develop
git checkout staging
git merge develop
git push origin staging
git push staging-heroku staging:master
git checkout master
git merge develop
git push origin master
git push production-heroku master:master
```

### References
[node.js Heroku Deployment](https://devcenter.heroku.com/articles/nodejs)

[node.js](http://nodejs.org/)

[express](http://expressjs.com/)

[Coursera: Startup Engineering](https://class.coursera.org/startup-001/class/index)


