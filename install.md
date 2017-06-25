# install nodejs to launch angularjs
## Related reference site
```
https://gruntjs.com/project-scaffolding
https://www.npmjs.com/package/grunt-serve
https://nodejs.org/en/download/package-manager/
https://www.npmjs.com/package/angular
https://nodejs.org/en/
http://yeoman.io/learning/
http://yeoman.io/codelab/setup.html
```
## Remove previously installed stuff
```
sudo npm remove -g yo
sudo npm remove -g karma
sudo npm remove -g generator-karma
sudo npm remove -g generator-angular
sudo npm remove -g bower
sudo npm remove -g grunt-cli
sudo npm remove -g grunt
sudo npm remove -g grunt-serve

sudo apt-get update
sudo apt-get remove npm
sudo apt-get remove nodejs
sudo rmdir -R /usr/lib/node-module/
```
## Force installation of nodejs with latest version
```
#curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
#sudo apt-get install -y nodejs
```
## Reinstall nodejs component
```
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
sudo apt-get install -y build-essescial

node --version && npm --version
v8.1.2
5.0.3
```
## Install NPM package
```
sudo npm install --global grunt
sudo npm install --global grunt-serve
sudo npm install --global grunt-cli
sudo npm install --global grunt-init
sudo npm install --global bower
sudo npm install --global generator-angular
sudo npm install --global yo
sudo npm install --global karma
sudo npm install --global generator-karma
```
## Run yo and select 'Install a generator' and input 'angular'
```
$ sudo yo
? 'Allo jdlee! What would you like to do? Install a generator
? Search npm for generators: angular
? Here's what I found. Official generator → angular
  Install one? (Use arrow keys)
❯ angular ෴  Yeoman generator for AngularJS 
  3m5-angular-1 * Install Yeoman (http://yeoman.io/)

 * `npm i -g generator-3m5-angular-1` 

 * `yo 3m5-angular-1` inside of an empty folder, it will create project structure and install dependencies

 * Start development server using `grunt dev` (currently only grunt opti 
  540-angular Yeoman generator for 540 using Angular JS and Gulp 
  a2lib A generator for angular 2 libraries with all the basic stuff setup to get you started quickly. Edit 
  a3 ACUBED Main Generator : JohnPapa AngularJS Style Guide + Yeoman generator for creating MEAN stack applications, using Mongo
DB, Express, AngularJS, and Node with generator-angular-fullstack v2.0.13 
  aaal An crud interface generator for loopback and angular. 
  abacus-fullstack Yeoman generator for creating MEAN stack applications, using MongoDB, Express, AngularJS, and Node and modifi
ed generator-angular-fullstack 
(Move up and down to reveal more choices)

     _-----_     ╭───────────────────────╮
    |       |    │      Bye from us!     │
    |--(o)--|    │       Chat soon.      │
   `---------´   │      Yeoman team      │
    ( _´U`_ )    │    http://yeoman.io   │
    /___A___\   /╰───────────────────────╯
     |  ~  |     
   __'.___.'__   
 ´   `  |° ´ Y ` 

$ 

```
## Create project
```
mkdir StockDog && cd StockDog
```
## Rerun yo and crete default project. Look created folder.
```
This generator can also be run with: yo angular


     _-----_     
    |       |    ╭──────────────────────────╮
    |--(o)--|    │    Welcome to Yeoman,    │
   `---------´   │   ladies and gentlemen!  │
    ( _´U`_ )    ╰──────────────────────────╯
    /___A___\   /
     |  ~  |     
   __'.___.'__   
 ´   `  |° ´ Y ` 

Out of the box I include Bootstrap and some AngularJS recommended modules.

? Would you like to use Gulp (experimental) instead of Grunt? No
? Would you like to use Sass (with Compass)? Yes
? Would you like to include Bootstrap? No
? Which modules would you like to include? angular-animate.js, angular-cookies.js, angular-resource.js, angular-route.js, angula
r-sanitize.js, angular-touch.js
   create app/styles/main.scss
   create app/index.html
   create bower.json
   create .bowerrc
   create package.json
   create Gruntfile.js
   create README.md
   invoke   angular:common:/usr/lib/node_modules/generator-angular/app/index.js
   create     .editorconfig
   create     .gitattributes
   create     .jscsrc
   create     .jshintrc
   create     .yo-rc.json
   create     .gitignore
   create     test/.jshintrc
   create     app/404.html
   create     app/favicon.ico
   create     app/robots.txt
   create     app/views/main.html
   create     app/images/yeoman.png
   invoke   angular:main:/usr/lib/node_modules/generator-angular/app/index.js
   create     app/scripts/app.js
   invoke   angular:controller:/usr/lib/node_modules/generator-angular/app/index.js
   create     app/scripts/controllers/main.js
   create     test/spec/controllers/main.js
Error  

You don't seem to have a generator with the name “karma:app” installed.
But help is on the way:

tree StockDog/
StockDog/
├── app
│   ├── 404.html
│   ├── favicon.ico
│   ├── images
│   │   └── yeoman.png
│   ├── index.html
│   ├── robots.txt
│   ├── scripts
│   │   ├── app.js
│   │   └── controllers
│   │       └── main.js
│   ├── styles
│   │   └── main.scss
│   └── views
│       └── main.html
├── bower.json
├── Gruntfile.js
├── package.json
├── README.md
└── test
    └── spec
        └── controllers
            └── main.js

9 directories, 14 files
jdlee@LeeJD:~$ 
```
```
sudo npm install --global karma

$ sudo npm install --global generator-fountain-webapp

$ sudo npm update -g npm
$ sudo yo angular --StockDog

$ yo --version
2.0.0

```
## Update generator
```
@sudo yo doctor
@ sudo yo 
  >> Update generator

npm install -g generator-angular-webapp
  
```
## Scaffolding StockDog
```
jdlee@LeeJD:~$ mkdir StockDog
jdlee@LeeJD:~$ cd StockDog/
jdlee@LeeJD:~/StockDog$ sudo yo
? 'Allo jdlee! What would you like to do? Angular

Make sure you are in the directory you want to scaffold into.
This generator can also be run with: yo angular


     _-----_     
    |       |    ╭──────────────────────────╮
    |--(o)--|    │    Welcome to Yeoman,    │
   `---------´   │   ladies and gentlemen!  │
    ( _´U`_ )    ╰──────────────────────────╯
    /___A___\   /
     |  ~  |     
   __'.___.'__   
 ´   `  |° ´ Y ` 

Out of the box I include Bootstrap and some AngularJS recommended modules.

? Would you like to use Gulp (experimental) instead of Grunt? No
? Would you like to use Sass (with Compass)? No
? Would you like to include Bootstrap? Yes
? Which modules would you like to include? angular-animate.js, angular-aria.js, angular-cookies.js, angular-resource.js, angular-messages.js, angular-r
lar-sanitize.js, angular-touch.js
   create app/styles/main.css
   create app/index.html
   create bower.json
   create .bowerrc
   create package.json
   create Gruntfile.js
   create README.md
   invoke   angular:common:/usr/lib/node_modules/generator-angular/app/index.js
   create     .editorconfig
   create     .gitattributes
   create     .jscsrc
   create     .jshintrc
   create     .yo-rc.json
   create     .gitignore
   create     test/.jshintrc
   create     app/404.html
   create     app/favicon.ico
   create     app/robots.txt
   create     app/views/main.html
   create     app/images/yeoman.png
   invoke   angular:main:/usr/lib/node_modules/generator-angular/app/index.js
   create     app/scripts/app.js
   invoke   angular:controller:/usr/lib/node_modules/generator-angular/app/index.js
   create     app/scripts/controllers/main.js
   create     test/spec/controllers/main.js
Error  

You don't seem to have a generator with the name “karma:app” installed.
But help is on the way:

You can see available generators via npm search yeoman-generator or via http://yeoman.io/generators/. 
Install them with npm install generator-karma:app.

To see all your installed generators run yo without any arguments. Adding the --help option will also show subgenerators. 

If yo cannot find the generator, run yo doctor to troubleshoot your system.

     _-----_     ╭───────────────────────╮
    |       |    │      Bye from us!     │
    |--(o)--|    │       Chat soon.      │
   `---------´   │      Yeoman team      │
    ( _´U`_ )    │    http://yeoman.io   │
    /___A___\   /╰───────────────────────╯
     |  ~  |     
   __'.___.'__   
 ´   `  |° ´ Y ` 

```
