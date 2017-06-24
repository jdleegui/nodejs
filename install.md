# install nodejs to launch angularjs
## Download nodejs
```
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
sudo apt install nodejs-legacy
```
## Check installation status
```
$ node -v
v4.2.6
$ npm -v
3.5.2
```
## Install Grunt, Bower
```
$ sudo npm remove –g grunt-cli
$ sudo npm remove –g bower
$ sudo npm remove –g generator-angular@0.9.8
$ sudo npm remove -g yo

$ sudo npm install –g grunt-cli
$ sudo npm install –g bower
$ sudo npm install –g generator-angular@0.9.8
$ sudo npm install -g yo
$ sudo npm install -g karma
```
## Scaffolding StockDog
```
´   │   ladies and gentlemen!  │
    ( _´U`_ )    ╰──────────────────────────╯
    /___A___\   /
     |  ~  |     
   __'.___.'__   
 ´   `  |° ´ Y ` 

Out of the box I include Bootstrap and some AngularJS recommended modules.

? Would you like to use Gulp (experimental) instead of Grunt? No
? Would you like to use Sass (with Compass)? No
? Would you like to include Bootstrap? Yes
? Which modules would you like to include? angular-animate.js, angular-cookies.js, angular-resource.js, angular-route.js, angular-sanitize.js, angular-touch.js
   create app/styles/main.css
 conflict app/index.html
? Overwrite app/index.html? overwrite
    force app/index.html
 conflict bower.json
? Overwrite bower.json? overwrite
    force bower.json
   create .bowerrc
 conflict package.json
? Overwrite package.json? overwrite
    force package.json
 conflict Gruntfile.js
? Overwrite Gruntfile.js? overwrite
    force Gruntfile.js
   create README.md
   invoke   angular:common:/usr/local/lib/node_modules/generator-angular/app/index.js
identical     .editorconfig
identical     .gitattributes
   create     .jscsrc
 conflict     .jshintrc
? Overwrite .jshintrc? overwrite
    force     .jshintrc
   create     .yo-rc.json
 conflict     .gitignore
? Overwrite .gitignore? overwrite this and all others
    force     .gitignore
    force     test/.jshintrc
    force     app/404.html
identical     app/favicon.ico
    force     app/robots.txt
    force     app/views/main.html
identical     app/images/yeoman.png
   invoke   angular:main:/usr/local/lib/node_modules/generator-angular/app/index.js
 conflict     app/scripts/app.js
? Overwrite app/scripts/app.js? overwrite this and all others
    force     app/scripts/app.js
   invoke   angular:controller:/usr/local/lib/node_modules/generator-angular/app/index.js
 conflict     app/scripts/controllers/main.js
? Overwrite app/scripts/controllers/main.js? overwrite this and all others
    force     app/scripts/controllers/main.js
    force     test/spec/controllers/main.js
Error angular StockDog 

You don't seem to have a generator with the name “karma:app” installed.
But help is on the way:

You can see available generators via npm search yeoman-generator or via http://yeoman.io/generators/. 
Install them with npm install generator-karma:app.

To see all your installed generators run yo without any arguments. Adding the --help option will also show subgenerators. 

If yo cannot find the generator, run yo doctor to troubleshoot your system.
$ 
```
