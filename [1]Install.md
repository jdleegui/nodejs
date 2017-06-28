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
https://github.com/swateek/angularjs
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
jdlee@LeeJD:~/StockDog$ sudo yo angular StockDog

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
? Which modules would you like to include? angular-animate.js, angular-cookies.js, angular-resource.js, angular-route.js, angular-sanitize.js, angular-touch.js
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
bower bootstrap#^3.2.0      not-cached https://github.com/twbs/bootstrap.git#^3.2.0 script for preinstall, continuing
bower bootstrap#^3.2.0         resolve https://github.com/twbs/bootstrap.git#^3.2.0
bower angular-resource#^1.4.0   cached https://github.com/angular/bower-angular-resource.git#1.6.4
bower angular-resource#^1.4.0 validate 1.6.4 against https://github.com/angular/bower-angular-resource.git#^1.4.0
bower angular#^1.4.0            cached https://github.com/angular/bower-angular.git#1.6.4
bower angular#^1.4.0          validate 1.6.4 against https://github.com/angular/bower-angular.git#^1.4.0
bower angular-cookies#^1.4.0    cached https://github.com/angular/bower-angular-cookies.git#1.6.4
bower angular-cookies#^1.4.0  validate 1.6.4 against https://github.com/angular/bower-angular-cookies.git#^1.4.0
bower angular-animate#^1.4.0    cached https://github.com/angular/bower-angular-animate.git#1.6.4
bower angular-animate#^1.4.0  validate 1.6.4 against https://github.com/angular/bower-angular-animate.git#^1.4.0
bower angular-sanitize#^1.4.0   cached https://github.com/angular/bower-angular-sanitize.git#1.6.4
bower angular-sanitize#^1.4.0 validate 1.6.4 against https://github.com/angular/bower-angular-sanitize.git#^1.4.0
bower angular-route#^1.4.0      cached https://github.com/angular/bower-angular-route.git#1.6.4
bower angular-route#^1.4.0    validate 1.6.4 against https://github.com/angular/bower-angular-route.git#^1.4.0
bower angular-touch#^1.4.0      cached https://github.com/angular/bower-angular-touch.git#1.6.4
bower angular-touch#^1.4.0    validate 1.6.4 against https://github.com/angular/bower-angular-touch.git#^1.4.0
bower angular-mocks#^1.4.0      cached https://github.com/angular/bower-angular-mocks.git#1.6.4
bower angular-mocks#^1.4.0    validate 1.6.4 against https://github.com/angular/bower-angular-mocks.git#^1.4.0
npm WARN deprecated minimatch@0.2.14: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
bower bootstrap#^3.2.0        download https://github.com/twbs/bootstrap/archive/v3.3.7.tar.gzfetched in 367ms
npm WARN deprecated bower@1.8.0: ..psst! While Bower is maintained, we recommend Yarn and Webpack for *new* front-end projects! Yarn's advantage is security and reliability, and Webpack's is support for both CommonJS and AMD projects. Currently there's no migration path but we hope you'll help us figure out one.
npm WARN deprecated minimatch@2.0.10: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
npm WARN deprecated graceful-fs@1.2.3: graceful-fs v3.0.0 and before will fail on node releases >= v7.0. Please update to graceful-fs@^4.0.0 as soon as possible. Use 'npm ls graceful-fs' to find it in the tree.
npm WARN deprecated bower@1.3.12: ..psst! While Bower is maintained, we recommend Yarn and Webpack for *new* front-end projects! Yarn's advantage is security and reliability, and Webpack's is support for both CommonJS and AMD projects. Currently there's no migration path but we hope you'll help us figure out one.
bower bootstrap#^3.2.0         extract archive.tar.gzge manifest for lower-case-first@^1.0.0 fetched in 170ms
npm WARN deprecated minimatch@0.3.0: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
bower bootstrap#^3.2.0        resolved https://github.com/twbs/bootstrap.git#3.3.7maps@1.6.0 fetched in 254ms
npm WARN deprecated graceful-fs@2.0.3: graceful-fs v3.0.0 and before will fail on node releases >= v7.0. Please update to graceful-fs@^4.0.0 as soon as possible. Use 'npm ls graceful-fs' to find it in the tree.
bower jquery#1.9.1 - 3          cached https://github.com/jquery/jquery-dist.git#3.2.1d in 76ms
bower jquery#1.9.1 - 3        validate 3.2.1 against https://github.com/jquery/jquery-dist.git#1.9.1 - 3
bower angular-resource#^1.4.0  install angular-resource#1.6.4ifest for end-of-stream@1.0.0 fetched in 181ms
bower angular-cookies#^1.4.0   install angular-cookies#1.6.4
bower angular-animate#^1.4.0   install angular-animate#1.6.4
bower angular#^1.4.0           install angular#1.6.4
bower angular-sanitize#^1.4.0  install angular-sanitize#1.6.4
bower angular-touch#^1.4.0     install angular-touch#1.6.4
bower angular-route#^1.4.0     install angular-route#1.6.4
bower angular-mocks#^1.4.0     install angular-mocks#1.6.4
bower bootstrap#^3.2.0         install bootstrap#3.3.7
bower jquery#1.9.1 - 3         install jquery#3.2.1
npm WARN deprecated minimatch@1.0.0: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
npm WARN deprecated tough-cookie@0.12.1: ReDoS vulnerability parsing Set-Cookie https://nodesecurity.io/advisories/130
npm WARN deprecated node-uuid@1.4.8: Use uuid module instead
[ .................] | fetchMetadata: sill pacote range manifest for gulp-util@^3.0.1 fetched in 130ms
angular-resource#1.6.4 bower_components/angular-resource
└── angular#1.6.4

angular-cookies#1.6.4 bower_components/angular-cookies
└── angular#1.6.4

angular-animate#1.6.4 bower_components/angular-animate
└── angular#1.6.4

angular#1.6.4 bower_components/angular

angular-sanitize#1.6.4 bower_components/angular-sanitize
└── angular#1.6.4

angular-touch#1.6.4 bower_components/angular-touch
└── angular#1.6.4

angular-route#1.6.4 bower_components/angular-route
└── angular#1.6.4

angular-mocks#1.6.4 bower_components/angular-mocks
└── angular#1.6.4

bootstrap#3.3.7 bower_components/bootstrap
└── jquery#3.2.1

jquery#3.2.1 bower_components/jquery
npm WARN deprecated npmconf@2.1.2: this package has been reintegrated into npm and is now out of date with respect to npm
npm WARN prefer global jshint@2.8.0 should be installed with -g

> optipng-bin@3.1.4 postinstall /home/jdlee/StockDog/node_modules/optipng-bin
> node lib/install.js

  ✔ optipng pre-build test passed successfully

> jpegtran-bin@3.2.0 postinstall /home/jdlee/StockDog/node_modules/jpegtran-bin
> node lib/install.js

  ✔ jpegtran pre-build test passed successfully

> gifsicle@3.0.4 postinstall /home/jdlee/StockDog/node_modules/gifsicle
> node lib/install.js

  ✔ gifsicle pre-build test passed successfully
npm notice created a lockfile as package-lock.json. You should commit this file.
added 993 packages in 46.555s
Running "wiredep:app" (wiredep) task

Running "wiredep:test" (wiredep) task

Done, without errors.


Execution Time (2017-06-27 20:15:58 UTC+9)
loading tasks          118ms  ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 56%
loading grunt-wiredep    5ms  ▇▇▇▇▇ 2%
wiredep:app             81ms  ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 38%
wiredep:test             8ms  ▇▇▇▇▇▇▇ 4%
Total 212ms

? Overwrite package.json? overwrite this and all others
    force     package.json

> phantomjs-prebuilt@2.1.14 install /home/jdlee/StockDog/node_modules/phantomjs-prebuilt
> node install.js

PhantomJS not found on PATH
Downloading https://github.com/Medium/phantomjs/releases/download/v2.1.1/phantomjs-2.1.1-linux-x86_64.tar.bz2
Saving to /tmp/phantomjs/phantomjs-2.1.1-linux-x86_64.tar.bz2
Receiving...
  [=======================================-] 97%
Received 22866K total.
Extracting tar contents (via spawned process)
Removing /home/jdlee/StockDog/node_modules/phantomjs-prebuilt/lib/phantom
Copying extracted folder /tmp/phantomjs/phantomjs-2.1.1-linux-x86_64.tar.bz2-extract-1498562217218/phantomjs-2.1.1-linux-x86_64 -> /home/jdlee/StockDog/node_modules/phantomjs-prebuilt/lib/phantom
Writing location.js file
Done. Phantomjs binary available at /home/jdlee/StockDog/node_modules/phantomjs-prebuilt/lib/phantom/bin/phantomjs

> fsevents@1.1.2 install /home/jdlee/StockDog/node_modules/fsevents
> node install

+ karma-phantomjs-launcher@1.0.4
+ phantomjs-prebuilt@2.1.14
+ karma-jasmine@1.1.0
+ karma@1.7.0
+ jasmine-core@2.6.4
added 303 packages in 50.597s


   ╭─────────────────────────────────────╮
   │                                     │
   │   Update available 5.0.3 → 5.0.4    │
   │     Run npm i -g npm to update      │
   │                                     │
   ╰─────────────────────────────────────╯

jdlee@LeeJD:~/StockDog$ 
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
