### Update script

## Remove man.html,about.html
```
jdlee@LeeJD:~$ mv StkDog/app/views/main.html ~/BakStkDog/app/views/
jdlee@LeeJD:~$ mv StkDog/app/views/about.html ~/BakStkDog/app/views/
jdlee@LeeJD:~$ mv StkDog/app/scripts/controllers/main.js ~/BakStkDog/app/scripts/controllers/
jdlee@LeeJD:~$ mv StkDog/app/scripts/controllers/about.js ~/BakStkDog/app/scripts/controllers/

```
## Remove .when activator
```
jdlee@LeeJD:~$ cat  StkDog/app/scripts/app.js 
'use strict';

/**
 * @ngdoc overview
 * @name stkDogApp
 * @description
 * # stkDogApp
 *
 * Main module of the application.
 */
angular
  .module('stkDogApp', [
    'ngAnimate',
    'ngAria',
    'ngCookies',
    'ngMessages',
    'ngResource',
    'ngRoute',
    'ngSanitize',
    'ngTouch'
  ])
  .config(function ($routeProvider) {
    $routeProvider
/**
      .when('/', {
        templateUrl: 'views/main.html',
        controller: 'MainCtrl',
        controllerAs: 'main'
      })
      .when('/about', {
        templateUrl: 'views/about.html',
        controller: 'AboutCtrl',
        controllerAs: 'about'
      })
*/
      .otherwise({
        redirectTo: '/'
      });
  });
jdlee@LeeJD:~$ cat StkDog/app/index.html 
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <meta name="description" content="">
    <meta name="viewport" content="width=device-width">
    <!-- Place favicon.ico and apple-touch-icon.png in the root directory -->
    <!-- build:css(.) styles/vendor.css -->
    <!-- bower:css -->
    <!-- endbower -->
    <!-- endbuild -->
    <!-- build:css(.tmp) styles/main.css -->
    <link rel="stylesheet" href="styles/main.css">
    <!-- endbuild -->
  </head>
  <body ng-app="stkDogApp">
    <!--[if lte IE 8]>
      <p class="browsehappy">You are using an <strong>outdated</strong> browser. Please <a href="http://browsehappy.com/">upgrade your browser</a> to improve your experience.</p>
    <![endif]-->

    <!-- Add your site or application content here -->
    <div class="header">
      <div class="navbar navbar-default" role="navigation">
        <div class="container">
          <div class="navbar-header">

            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#js-navbar-collapse">
              <span class="sr-only">Toggle navigation</span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
            </button>

            <a class="navbar-brand" href="#/">stkDog</a>
          </div>

          <div class="collapse navbar-collapse" id="js-navbar-collapse">

            <ul class="nav navbar-nav">
              <li class="active"><a href="#/">Home</a></li>
              <li><a ng-href="#/about">About</a></li>
              <li><a ng-href="#/">Contact</a></li>
            </ul>
          </div>
        </div>
      </div>
    </div>

    <div class="container">
    <div ng-view=""></div>
    </div>

    <div class="footer">
      <div class="container">
        <p><span class="glyphicon glyphicon-heart"></span> from the Yeoman team</p>
      </div>
    </div>


    <!-- Google Analytics: change UA-XXXXX-X to be your site's ID -->
     <script>
       !function(A,n,g,u,l,a,r){A.GoogleAnalyticsObject=l,A[l]=A[l]||function(){
       (A[l].q=A[l].q||[]).push(arguments)},A[l].l=+new Date,a=n.createElement(g),
       r=n.getElementsByTagName(g)[0],a.src=u,r.parentNode.insertBefore(a,r)
       }(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

       ga('create', 'UA-XXXXX-X');
       ga('send', 'pageview');
    </script>

    <!-- build:js(.) scripts/vendor.js -->
    <!-- bower:js -->
    <!-- endbower -->
    <!-- endbuild -->

        <!-- build:js({.tmp,app}) scripts/scripts.js -->
        <script src="scripts/app.js"></script>
        <!-- <script src="scripts/controllers/main.js"></script>  -->
        <!-- <script src="scripts/controllers/about.js"></script> -->
        <!-- endbuild -->
</body>
</html>
jdlee@LeeJD:~$ 
```
## Install git client and angular-strap
```
jdlee@LeeJD:~/StkDog$ sudo apt-get install git
jdlee@LeeJD:~/StkDog$ bower install angular-strap
```
## Insert 'mgcrea.ngStrap'
```
jdlee@LeeJD:~$ cat StkDog/app/scripts/app.js 
'use strict';

/**
 * @ngdoc overview
 * @name stkDogApp
 * @description
 * # stkDogApp
 *
 * Main module of the application.
 */
angular
  .module('stkDogApp', [
    'ngAnimate',
    'ngAria',
    'ngCookies',
    'ngMessages',
    'ngResource',
    'ngRoute',
    'ngSanitize',
    'ngTouch',
    
    'mgcrea.ngStrap'
  ])
  .config(function ($routeProvider) {
    $routeProvider
    **
/**
      .when('/', {
        templateUrl: 'views/main.html',
        controller: 'MainCtrl',
        controllerAs: 'main'
      })
      .when('/about', {
        templateUrl: 'views/about.html',
        controller: 'AboutCtrl',
        controllerAs: 'about'
      })
*/
    **
      .otherwise({
        redirectTo: '/'
      });
  });
jdlee@LeeJD:~$ 
```
## Check if 'ng-app' is inserted automatically.
```
jdlee@LeeJD:~$ head StkDog/app/index.html -n 20
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <meta name="description" content="">
    <meta name="viewport" content="width=device-width">
    <!-- Place favicon.ico and apple-touch-icon.png in the root directory -->
    <!-- build:css(.) styles/vendor.css -->
    <!-- bower:css -->
    <!-- endbower -->
    <!-- endbuild -->
    <!-- build:css(.tmp) styles/main.css -->
    <link rel="stylesheet" href="styles/main.css">
    <!-- endbuild -->
  </head>
  <body __ng-app="stkDogApp"__ >
    <!--[if lte IE 8]>
      <p class="browsehappy">You are using an <strong>outdated</strong> browser. Please <a href="http://browsehappy.com/">upgrade your browser</a> to improve your experience.</p>
    <![endif]-->
jdlee@LeeJD:~$ 
```
