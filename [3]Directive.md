### Directives
## Add angular dirictives
```
jdlee@LeeJD:~/StkDog$ sudo yo angular:directive stk-Watchlist-Panel
```
## Edit script
```diff
-jdlee@LeeJD:~/StkDog$ cat app/scripts/directives/stk-watchlist-panel.js 
-'use strict';
-
-/**
- * @ngdoc directive
- * @name stkDogApp.directive:stkWatchlistPanel
- * @description
- * # stkWatchlistPanel
- */
-angular.module('stkDogApp')
-  .directive('stkWatchlistPanel', function () {
-    return {
-      template: '<div></div>',
-      restrict: 'E',
-      link: function postLink(scope, element, attrs) {
-        element.text('this is the stkWatchlistPanel directive');
-      }
-    };
-  });
```
```diff
+jdlee@LeeJD:~/StkDog$ vim app/scripts/directives/stk-watchlist-panel.js 
+jdlee@LeeJD:~/StkDog$ cat app/scripts/directives/stk-watchlist-panel.js 
+'use strict';
+
+/**
+ * @ngdoc directive
+ * @name stkDogApp.directive:stkWatchlistPanel
+ * @description
+ * # stkWatchlistPanel
+ */
+angular.module('stkDogApp')
-  /*
-  .directive('stkWatchlistPanel', function () {
-    return {
-      template: '<div></div>',
-      restrict: 'E',
-      link: function postLink(scope, element, attrs) {
-        element.text('this is the stkWatchlistPanel directive');
-      }
-    };
-  });
-  */
+  .directive('stkWatchlistPanel', function ($location, $modal, WatchlistService) {
+    return {
+      templateUrl: 'views/templates/watchlist-panel.html',
+      restrict: 'E',
+      scope: {},
+      link: function ($scope) {
+        // [2] Initialize variables
+        $scope.watchlist = {};
+        var addListModal = $modal({
+          scope: $scope,
+          template: 'views/templates/addlist-modal.html',
+          show: false
+        });
+        // [3] Bind model from service to this scope
+        $scope.watchlists = WatchlistService.query();
+        // [4] Display addlist modal
+        $scope.showModal = function () {
+          addListModal.$promise.then(addListModal.show);
+        };
+        // [5] Create a new list from fields in modal
+        $scope.createList = function () {
+          WatchlistService.save($scope.watchlist);
+          addListModal.hide();
+          $scope.watchlist = {};
+        };
+        // [6] Delete desired list and redirect to home
+          $scope.deleteList = function (list) {
+          WatchlistService.remove(list);
+          $location.path('/');
+        };
+      }
+    };
+  });
```
## Create watchlist-panel.html
```
jdlee@LeeJD:~/StkDog$ mkdir app/views/templates
jdlee@LeeJD:~/StkDog$ vim app/views/templates/watchlist‐panel.html
jdlee@LeeJD:~/StkDog$ cat app/views/templates/watchlist‐panel.html
<div class="panel panel-info">
  <div class="panel-heading">
    <span class="glyphicon glyphicon-eye-open"></span>
    Watchlists
    <!––[1] Invoke showModal() handler on click ––>
    <button type="button"
      class="btn btn-success btn-xs pull-right"
      ng-click="showModal()">
      <span class="glyphicon glyphicon-plus"></span>
    </button>
  </div>
  <div class="panel-body">
  <!–– [2] Show help text if no watchlists exist ––>
    <div ng-if="!watchlists.length" class="text-center">
      Use <span class="glyphicon glyphicon-plus"></span> to create a list
    </div>
    <div class="list-group">
    <!–– [3] Repeat over each list in watchlists and create link ––>
    <a class="list-group-item"
      ng-repeat="list in watchlists track by $index">
      {{list.name}}
      <!–– [4] Delete this list by invoking deleteList() handler ––>
      <button type="button" class="close"
        ng-click="deleteList(list)"> &times;
      </button>
    </a>
    </div>
  </div>
</div>
jdlee@LeeJD:~/StkDog$ 
```
## Create addlist-model.html
```
jdlee@LeeJD:~/StkDog$ cat app/views/templates/addlist‐modal.html
<div class="modal" tabindex="-1" role="dialog">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
      <!–– [1] Invoke $modal.$hide() on click ––>
      <button type="button" class="close"
        ng-click="$hide()"> &times;
      </button>
      <h4 class="modal-title">Create New Watchlist</h4>
      </div>
      <!–– [2] Name this form for validation purposes ––>
      <form role="form" id="add-list" name="listForm">
        <div class="modal-body">
          <div class="form-group">
            <label for="list-name">Name</label>
      <!–– [3] Bind input to watchlist.name ––>
      <input type="text"
        class="form-control"
        id="list-name"
        placeholder="Name this watchlist"
        ng-model="watchlist.name"
        required>
      </div>
      <div class="form-group">
        <label for="list-description">Brief Description</label>
        <!–– [4] Bind input to watchlist.description ––>
        <input type="text"
          class="form-control"
          id="list-description"
          maxlength="40"
          placeholder="Describe this watchlist"
          ng-model="watchlist.description"
          required>
        </div>
      </div>
      <div class="modal-footer">
        <!–– [5] Create list on click, but disable if form is invalid ––>
        <button type="submit"
          class="btn btn-success"
          ng-click="createList()"
          ng-disabled="!listForm.$valid">Create</button>
        <button type="button"
          class="btn btn-danger"
          ng-click="$hide()">Cancel</button>
        </div>
      </form>
    </div>
  </div>
</div>
jdlee@LeeJD:~/StkDog$ 
```
