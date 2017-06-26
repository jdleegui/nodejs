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
## Create project
```
jdlee@LeeJD:~$ mkdir StkDog
jdlee@LeeJD:~$ cd StkDog/
```
## Run yo and select 'Install a generator' and input 'angular'
```
jdlee@LeeJD:~/StkDog$ sudo yo 
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
? Would you like to use Sass (with Compass)? Yes
? Would you like to include Bootstrap? Yes
? Would you like to use the Sass version of Bootstrap? Yes
? Which modules would you like to include? angular-animate.js, angular-aria.js, angular-cookies.js, angular-resource.js, angular-messages.js, angular-route.js, angular-sanitize.j
s, angular-touch.js
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
   invoke   karma:app


I'm all done. Running bower install & npm install for you to install the required dependencies. If this fails, try running the command yourself.


   invoke       angular:route
   invoke           angular:controller:/usr/lib/node_modules/generator-angular/route/index.js
   create             app/scripts/controllers/about.js
   create             test/spec/controllers/about.js
   invoke           angular:view:/usr/lib/node_modules/generator-angular/route/index.js
   create             app/views/about.html
   create     test/karma.conf.js
 conflict     package.json
bower angular#^1.4.0            ENOGIT git is not installed or not in the PATHal: verb npm-session b58ee77a3b8d7283
grunt-cli: The grunt command line interface (v1.2.0)

Fatal error: Unable to find local grunt.

If you're seeing this message, grunt hasn't been installed locally to
your project. For more information about installing and configuring grunt,
please see the Getting Started guide:

http://gruntjs.com/getting-started
npm WARN deprecated minimatch@0.2.14: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
npm WARN deprecated bower@1.8.0: ..psst! While Bower is maintained, we recommend Yarn and Webpack for *new* front-end projects! Yarn's advantage is security and reliability, and Webpack's is support for both CommonJS and AMD projects. Currently there's no migration path but we hope you'll help us figure out one.
npm WARN deprecated minimatch@2.0.10: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
npm WARN deprecated graceful-fs@1.2.3: graceful-fs v3.0.0 and before will fail on node releases >= v7.0. Please update to graceful-fs@^4.0.0 as soon as possible. Use 'npm ls graceful-fs' to find it in the tree.
npm WARN deprecated bower@1.3.12: ..psst! While Bower is maintained, we recommend Yarn and Webpack for *new* front-end projects! Yarn's advantage is security and reliability, and Webpack's is support for both CommonJS and AMD projects. Currently there's no migration path but we hope you'll help us figure out one.
npm WARN deprecated minimatch@0.3.0: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
npm WARN deprecated graceful-fs@2.0.3: graceful-fs v3.0.0 and before will fail on node releases >= v7.0. Please update to graceful-fs@^4.0.0 as soon as possible. Use 'npm ls graceful-fs' to find it in the tree.
npm WARN deprecated minimatch@1.0.0: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
npm WARN deprecated node-uuid@1.4.8: Use uuid module instead
npm WARN deprecated tough-cookie@0.12.1: ReDoS vulnerability parsing Set-Cookie https://nodesecurity.io/advisories/130
npm WARN deprecated npmconf@2.1.2: this package has been reintegrated into npm and is now out of date with respect to npm
npm WARN prefer global jshint@2.8.0 should be installed with -g

> optipng-bin@3.1.4 postinstall /home/jdlee/StkDog/node_modules/optipng-bin
> node lib/install.js

  ✔ optipng pre-build test passed successfully

> jpegtran-bin@3.2.0 postinstall /home/jdlee/StkDog/node_modules/jpegtran-bin
> node lib/install.js

  ✔ jpegtran pre-build test passed successfully

> gifsicle@3.0.4 postinstall /home/jdlee/StkDog/node_modules/gifsicle
> node lib/install.js

  ✔ gifsicle pre-build test passed successfully
npm notice created a lockfile as package-lock.json. You should commit this file.
added 997 packages in 24.253s
? Overwrite package.json? overwrite this and all others
    force     package.json

> phantomjs-prebuilt@2.1.14 install /home/jdlee/StkDog/node_modules/phantomjs-prebuilt
> node install.js

PhantomJS not found on PATH
Download already available at /tmp/phantomjs/phantomjs-2.1.1-linux-x86_64.tar.bz2
Verified checksum of previously downloaded file
Extracting tar contents (via spawned process)

Removing /home/jdlee/StkDog/node_modules/phantomjs-prebuilt/lib/phantom
Copying extracted folder /tmp/phantomjs/phantomjs-2.1.1-linux-x86_64.tar.bz2-extract-1498465037090/phantomjs-2.1.1-linux-x86_64 -> /home/jdlee/StkDog/node_modules/phantomjs-prebuilt/lib/phantom
Writing location.js file
Done. Phantomjs binary available at /home/jdlee/StkDog/node_modules/phantomjs-prebuilt/lib/phantom/bin/phantomjs

> fsevents@1.1.2 install /home/jdlee/StkDog/node_modules/fsevents
> node install

+ karma-jasmine@1.1.0
+ karma@1.7.0
+ jasmine-core@2.6.4
+ karma-phantomjs-launcher@1.0.4
+ phantomjs-prebuilt@2.1.14
added 302 packages in 16.605s

     _-----_     ╭───────────────────────╮
    |       |    │      Bye from us!     │
    |--(o)--|    │       Chat soon.      │
   `---------´   │      Yeoman team      │
    ( _´U`_ )    │    http://yeoman.io   │
    /___A___\   /╰───────────────────────╯
     |  ~  |     
   __'.___.'__   
 ´   `  |° ´ Y ` 

jdlee@LeeJD:~/StkDog$ 
```
## RUN using grunt serve comand and check in localhost:9000
```
jdlee@LeeJD:~/StkDog$ 
jdlee@LeeJD:~/StkDog$ grunt serve
Running "serve" task

Running "clean:server" (clean) task
>> 0 paths cleaned.

Running "wiredep:app" (wiredep) task
Warning: Error: Cannot find where you keep your Bower packages. Use --force to continue.

Aborted due to warnings.


Execution Time (2017-06-26 17:17:30 UTC+9)
loading tasks                109ms  ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 58%
serve                          3ms  ▇▇▇ 2%
loading grunt-contrib-clean    4ms  ▇▇▇ 2%
clean:server                   5ms  ▇▇▇▇ 3%
wiredep:app                   65ms  ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 35%
Total 188ms

jdlee@LeeJD:~/StkDog$ grunt serve --force
Running "serve" task

Running "clean:server" (clean) task
>> 0 paths cleaned.

Running "wiredep:app" (wiredep) task
Warning: Error: Cannot find where you keep your Bower packages. Used --force, continuing.

Running "wiredep:test" (wiredep) task
Warning: Error: Cannot find where you keep your Bower packages. Used --force, continuing.

Running "wiredep:sass" (wiredep) task
Warning: Error: Cannot find where you keep your Bower packages. Used --force, continuing.

Running "concurrent:server" (concurrent) task
    
    Running "compass:server" (compass) task
    Warning: not found: compass Used --force, continuing.
    
    Done, but with warnings.
    
    
    Execution Time (2017-06-26 17:17:36 UTC+9)
    loading tasks                  108ms  ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 79%
    loading grunt-contrib-compass   20ms  ▇▇▇▇▇ 15%
    compass:server                   8ms  ▇▇ 6%
    Total 136ms
    
Running "postcss:server" (postcss) task

Running "connect:livereload" (connect) task
Started connect web server on http://localhost:9000

Running "watch" task
Waiting...
^C

Execution Time (2017-06-26 17:17:36 UTC+9)
loading tasks      111ms  ▇▇ 1%
concurrent:server  343ms  ▇▇▇▇▇▇▇ 4%
Total 7.8s


```
