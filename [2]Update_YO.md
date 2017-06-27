### Update script

## Remove man.html,about.html
```
jdlee@LeeJD:~/StockDog$ mkdir ~/BakStockDog
jdlee@LeeJD:~/StockDog$ mkdir ~/BakStockDog/app
jdlee@LeeJD:~/StockDog$ mkdir ~/BakStockDog/app/views
jdlee@LeeJD:~/StockDog$ mv app/views/main.html ~/BakStockDog/app/views/
jdlee@LeeJD:~/StockDog$ mv app/views/about.html ~/BakStockDog/app/views/
jdlee@LeeJD:~/StockDog$ mkdir ~/BakStockDog/app/scripts/
jdlee@LeeJD:~/StockDog$ mkdir ~/BakStockDog/app/scripts/controllers/
jdlee@LeeJD:~/StockDog$ mv app/scripts/controllers/main.js ~/BakStockDog/app/scripts/controllers/
jdlee@LeeJD:~/StockDog$ mv app/scripts/controllers/about.js ~/BakStockDog/app/scripts/controllers/

```
## Remove .when activator
```diff
jdlee@LeeJD:~/StockDog$ cp app/scripts/app.js ~/BakStockDog/app/scripts/
jdlee@LeeJD:~/StockDog$ cat app/scripts/app.js 
'use strict';

/**
 * @ngdoc overview
 * @name stockDogApp
 * @description
 * # stockDogApp
 *
 * Main module of the application.
 */
angular
  .module('stockDogApp', [
    'ngAnimate',
    'ngCookies',
    'ngResource',
    'ngRoute',
    'ngSanitize',
    'ngTouch'
  ])
  .config(function ($routeProvider) {
    $routeProvider
-      .when('/', {
-        templateUrl: 'views/main.html',
-        controller: 'MainCtrl',
-        controllerAs: 'main'
-      })
-      .when('/about', {
-        templateUrl: 'views/about.html',
-        controller: 'AboutCtrl',
-        controllerAs: 'about'
-      })
      .otherwise({
        redirectTo: '/'
      });
  });
```
## like this
```
jdlee@LeeJD:~/StockDog$ vim app/scripts/app.js 
jdlee@LeeJD:~/StockDog$ cat app/scripts/app.js 
'use strict';

/**
 * @ngdoc overview
 * @name stockDogApp
 * @description
 * # stockDogApp
 *
 * Main module of the application.
 */
angular
  .module('stockDogApp', [
    'ngAnimate',
    'ngCookies',
    'ngResource',
    'ngRoute',
    'ngSanitize',
    'ngTouch'
  ])
  .config(function ($routeProvider) {
    $routeProvider
     .otherwise({
        redirectTo: '/'
      });
  });
jdlee@LeeJD:~/StockDog$ 
```
## Unlink reference from index.html
```diff
jdlee@LeeJD:~/StockDog$ cp app/index.html ~/BakStockDog/app/index_01.html
jdlee@LeeJD:~/StockDog$ cat app/index.html 
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
    <link rel="stylesheet" href="bower_components/bootstrap/dist/css/bootstrap.css" />
    <!-- endbower -->
    <!-- endbuild -->
    <!-- build:css(.tmp) styles/main.css -->
    <link rel="stylesheet" href="styles/main.css">
    <!-- endbuild -->
  </head>
  <body ng-app="stockDogApp">
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

            <a class="navbar-brand" href="#/">stockDog</a>
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
    <script src="bower_components/jquery/dist/jquery.js"></script>
    <script src="bower_components/angular/angular.js"></script>
    <script src="bower_components/bootstrap/dist/js/bootstrap.js"></script>
    <script src="bower_components/angular-animate/angular-animate.js"></script>
    <script src="bower_components/angular-cookies/angular-cookies.js"></script>
    <script src="bower_components/angular-resource/angular-resource.js"></script>
    <script src="bower_components/angular-route/angular-route.js"></script>
    <script src="bower_components/angular-sanitize/angular-sanitize.js"></script>
    <script src="bower_components/angular-touch/angular-touch.js"></script>
    <!-- endbower -->
    <!-- endbuild -->

        <!-- build:js({.tmp,app}) scripts/scripts.js -->
        <script src="scripts/app.js"></script>
-        <script src="scripts/controllers/main.js"></script>
-        <script src="scripts/controllers/about.js"></script>
        <!-- endbuild -->
</body>
</html>
```
## like this
```
jdlee@LeeJD:~/StockDog$ vim app/index.html 
jdlee@LeeJD:~/StockDog$ cat app/index.html 
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
    <link rel="stylesheet" href="bower_components/bootstrap/dist/css/bootstrap.css" />
    <!-- endbower -->
    <!-- endbuild -->
    <!-- build:css(.tmp) styles/main.css -->
    <link rel="stylesheet" href="styles/main.css">
    <!-- endbuild -->
  </head>
  <body ng-app="stockDogApp">
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

            <a class="navbar-brand" href="#/">stockDog</a>
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
    <script src="bower_components/jquery/dist/jquery.js"></script>
    <script src="bower_components/angular/angular.js"></script>
    <script src="bower_components/bootstrap/dist/js/bootstrap.js"></script>
    <script src="bower_components/angular-animate/angular-animate.js"></script>
    <script src="bower_components/angular-cookies/angular-cookies.js"></script>
    <script src="bower_components/angular-resource/angular-resource.js"></script>
    <script src="bower_components/angular-route/angular-route.js"></script>
    <script src="bower_components/angular-sanitize/angular-sanitize.js"></script>
    <script src="bower_components/angular-touch/angular-touch.js"></script>
    <!-- endbower -->
    <!-- endbuild -->

        <!-- build:js({.tmp,app}) scripts/scripts.js -->
        <script src="scripts/app.js"></script>
       <!-- endbuild -->
</body>
</html>
jdlee@LeeJD:~/StockDog$ 
```
## Install git client and angular-strap
```
jdlee@LeeJD:~/StockDog$ sudo apt-get install git
jdlee@LeeJD:~/StockDog$ bower install angular-strap –save
bower angular-strap#*           cached https://github.com/mgcrea/angular-strap.git#2.3.12
bower angular-strap#*         validate 2.3.12 against https://github.com/mgcrea/angular-strap.git#*
bower                        ENOTFOUND Package –save not found
```
## Insert 'mgcrea.ngStrap'
```diff
jdlee@LeeJD:~/StockDog$ cat app/scripts/app.js 
'use strict';

/**
 * @ngdoc overview
 * @name stockDogApp
 * @description
 * # stockDogApp
 *
 * Main module of the application.
 */
angular
  .module('stockDogApp', [
    'ngAnimate',
    'ngCookies',
    'ngResource',
    'ngRoute',
    'ngSanitize',
-   'ngTouch'
+   'ngTouch',
+   'mgcrea.ngStrap'
   ])
  .config(function ($routeProvider) {
    $routeProvider
     .otherwise({
        redirectTo: '/'
      });
  });
jdlee@LeeJD:~/StockDog$ vim app/scripts/app.js 
```
## Like this
```
jdlee@LeeJD:~/StockDog$ cat app/scripts/app.js 
'use strict';

/**
 * @ngdoc overview
 * @name stockDogApp
 * @description
 * # stockDogApp
 *
 * Main module of the application.
 */
angular
  .module('stockDogApp', [
    'ngAnimate',
    'ngCookies',
    'ngResource',
    'ngRoute',
    'ngSanitize',
    'ngTouch',
    'mgcrea.ngStrap'
  ])
  .config(function ($routeProvider) {
    $routeProvider
     .otherwise({
        redirectTo: '/'
      });
  });
jdlee@LeeJD:~/StockDog$ 
```
## Insert 'mgcrea.ngStrap'
```
  ])
  .config(function ($routeProvider) {
    $routeProvider
    **
```
```diff
-/**
-      .when('/', {
-        templateUrl: 'views/main.html',
-        controller: 'MainCtrl',
-        controllerAs: 'main'
-      })
-      .when('/about', {
-        templateUrl: 'views/about.html',
-        controller: 'AboutCtrl',
-        controllerAs: 'about'
-      })
-*/
```
```
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
  ```
  ```diff
  + <body ng-app="stkDogApp">
  - <body>
  ```
  ```
    <!--[if lte IE 8]>
      <p class="browsehappy">You are using an <strong>outdated</strong> browser. Please <a href="http://browsehappy.com/">upgrade your browser</a> to improve your experience.</p>
    <![endif]-->
jdlee@LeeJD:~$ 
```
## Add watch list
```
jdlee@LeeJD:~/StkDog$ yo angular:service Watchlist-Service
   create app/scripts/services/watchlist-service.js
   create test/spec/services/watchlist-service.js
jdlee@LeeJD:~/StkDog$ 
```
## Check if watchlist is included.
```
jdlee@LeeJD:~$ cat StkDog/app/index.html | grep 'watch'
        <script src="scripts/services/watchlist-service.js"></script>
jdlee@LeeJD:~$ 
```
## Install lodash
```
jdlee@LeeJD:~/StkDog$ bower install lodash --save
bower lodash#*              not-cached https://github.com/lodash/lodash.git#*
bower lodash#*                 resolve https://github.com/lodash/lodash.git#*
bower lodash#*                download https://github.com/lodash/lodash/archive/4.17.4.tar.gz
bower lodash#*                 extract archive.tar.gz
bower lodash#*                resolved https://github.com/lodash/lodash.git#4.17.4
bower lodash#^4.17.4           install lodash#4.17.4

lodash#4.17.4 bower_components/lodash
jdlee@LeeJD:~/StkDog$ 
```
## Update lodash
```
jdlee@LeeJD:~/StkDog$ bower install lodash --save
bower lodash#*                  cached https://github.com/lodash/lodash.git#4.17.4
bower lodash#*                validate 4.17.4 against https://github.com/lodash/lodash.git#*
```
```diff
-jdlee@LeeJD:~/StkDog$ cat app/scripts/services/watchlist-service.js 
-'use strict';
-
-/**
- * @ngdoc service
- * @name stkDogApp.WatchlistService
- * @description
- * # WatchlistService
- * Service in the stkDogApp.
- */
-angular.module('stkDogApp')
-  .service('WatchlistService', function () {
-    // AngularJS will instantiate a singleton by calling "new" on this function
-  });
+jdlee@LeeJD:~/StkDog$ vim app/scripts/services/watchlist-service.js 
+jdlee@LeeJD:~/StkDog$ cat app/scripts/services/watchlist-service.js 
+'use strict';
+
+/**
+ * @ngdoc service
+ * @name stkDogApp.WatchlistService
+ * @description
+ * # WatchlistService
+ * Service in the stkDogApp.
+ */
+angular.module('stkDogApp')
+    .service('WatchlistService', function WatchlistService() {
+    // [1] Helper: Load watchlists from localStorage
+    var loadModel = function () {
+        var model = {
+            watchlists: localStorage['StockDog.watchlists'] ?
+            JSON.parse(localStorage['StockDog.watchlists']) : [],
+            nextId: localStorage['StockDog.nextId'] ?
+            parseInt(localStorage['StockDog.nextId']) : 0
+        };
+    return model;
+    };
+
+    // [2] Helper: Save watchlists to localStorage
+    var saveModel = function () {
+        localStorage['StockDog.watchlists'] = JSON.stringify(Model.watchlists);
+        localStorage['StockDog.nextId'] = Model.nextId;
+    };
+
+    // [3] Helper: Use lodash to find a watchlist with given ID
+    var findById = function (listId) {
+        return _.find(Model.watchlists, function (watchlist) {
+            return watchlist.id === parseInt(listId);
+        });
+    };
+
+    // [4] Return all watchlists or find by given ID
+    this.query = function (listId) {
+        if (listId) {
+            return findById(listId);
+        } else {
+            return Model.watchlists;
+        }
+    };
+
+    // [5] Save a new watchlist to watchlists model
+    this.save = function (watchlist) {
+        watchlist.id = Model.nextId++;
+        Model.watchlists.push(watchlist);
+        saveModel();
+    };
+
+    // [6] Remove given watchlist from watchlists model
+    this.remove = function (watchlist) {
+        _.remove(Model.watchlists, function (list) {
+            return list.id === watchlist.id;
+        });
+        saveModel();
+    };
+
+    // [7] Initialize Model for this singleton service
+    var Model = loadModel();
+    });
+jdlee@LeeJD:~/StkDog$ 
```
