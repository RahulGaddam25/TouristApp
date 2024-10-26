  <meta charset="utf-8">
  <title>Bootstrap Position Tests</title>

  <link href="//netdna.bootstrapcdn.com/twitter-bootstrap/2.3.1/css/bootstrap-combined.no-icons.min.css" rel="stylesheet">
  <link href="//netdna.bootstrapcdn.com/font-awesome/3.0.2/css/font-awesome.css" rel="stylesheet">
  <link href="//netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css" rel="stylesheet">
  <link href="//netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.min.css" rel="stylesheet">

  <link rel="stylesheet" href="../test/vendor/stylesheets/jquery.qtip.css" type="text/css" media="screen">

@@ -18,6 +18,7 @@
  <script src="../test/vendor/javascripts/jquery-ui-1.10.2.custom.js"></script>

  <script src="../tourist.js"></script>
  <link rel="stylesheet" href="../tourist.css" type="text/css" media="screen">

  <!-- Tour js is defined here -->
  <script type="text/javascript">
@@ -108,4 +109,4 @@ <h1 id="main-heading" class="page-header">Test of positioning with Bootstrap pop
    <div class="target">This is the target</div>
  </div>
</body>
</html>
</html>
‎examples/bootstrap.html
+3
-3
Original file line number	Diff line number	Diff line change
@@ -4,8 +4,8 @@
  <meta charset="utf-8">
  <title>Bootstrap Example</title>

  <link href="//netdna.bootstrapcdn.com/twitter-bootstrap/2.3.1/css/bootstrap-combined.no-icons.min.css" rel="stylesheet">
  <link href="//netdna.bootstrapcdn.com/font-awesome/3.0.2/css/font-awesome.css" rel="stylesheet">
  <link href="//netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css" rel="stylesheet">
  <link href="//netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.min.css" rel="stylesheet">

  <script src="../test/vendor/javascripts/jquery-1.9.1.js"></script>
  <script src="../test/vendor/javascripts/underscore-1.4.4.js"></script>
@@ -104,4 +104,4 @@ <h1 id="main-heading" class="page-header">Tourist works with Bootstrap. Let me s

  </div>
</body>
</html>
</html>
‎examples/qtip.html
+3
-3
Original file line number	Diff line number	Diff line change
@@ -4,8 +4,8 @@
  <meta charset="utf-8">
  <title>QTip Example</title>

  <link href="//netdna.bootstrapcdn.com/twitter-bootstrap/2.3.1/css/bootstrap-combined.no-icons.min.css" rel="stylesheet">
  <link href="//netdna.bootstrapcdn.com/font-awesome/3.0.2/css/font-awesome.css" rel="stylesheet">
  <link href="//netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css" rel="stylesheet">
  <link href="//netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.min.css" rel="stylesheet">

  <link rel="stylesheet" href="../test/vendor/stylesheets/jquery.qtip.css" type="text/css" media="screen">

@@ -67,4 +67,4 @@ <h1 id="main-heading" class="page-header">Tourist works with QTip2. Let me show

  </div>
</body>
</html>
</html>
‎src/tip/base.coffee
+4
-4
Original file line number	Diff line number	Diff line change
@@ -10,12 +10,12 @@ class Tourist.Tip.Base
  _.extend @prototype, Backbone.Events

  # You can override any of thsee templates for your own stuff
  skipButtonTemplate: '<button class="btn btn-small pull-right tour-next">Skip this step →</button>'
  nextButtonTemplate: '<button class="btn btn-primary btn-small pull-right tour-next">Next step →</button>'
  finalButtonTemplate: '<button class="btn btn-primary btn-small pull-right tour-next">Finish up</button>'
  skipButtonTemplate: '<button class="btn btn-default btn-sm pull-right tour-next">Skip this step →</button>'
  nextButtonTemplate: '<button class="btn btn-primary btn-sm pull-right tour-next">Next step →</button>'
  finalButtonTemplate: '<button class="btn btn-primary btn-sm pull-right tour-next">Finish up</button>'

  closeButtonTemplate: '<a class="btn btn-close tour-close" href="#"><i class="icon icon-remove"></i></a>'
  okButtonTemplate: '<button class="btn btn-small tour-close btn-primary">Okay</button>'
  okButtonTemplate: '<button class="btn btn-sm tour-close btn-primary">Okay</button>'

  actionLabelTemplate: _.template '<h4 class="action-label"><%= label %></h4>'
  actionLabels: ['Do this:', 'Then this:', 'Next this:']
‎src/tip/qtip.coffee
+1
-1
Original file line number	Diff line number	Diff line change
@@ -17,7 +17,7 @@ class Tourist.Tip.QTip extends Tourist.Tip.Base
  # defaults for the qtip flyout.
  QTIP_DEFAULTS:
    content:
      text: ''
      text: ' '
    show:
      ready: false
      delay: 0
‎tourist.css
+6
-3
Original file line number	Diff line number	Diff line change
@@ -13,6 +13,7 @@
}
.popover .popover-content{
  padding: 10px 0 0 0;
  min-width: 200px;
}
.popover .popover-content p{
  margin: 0 8px 10px 8px;
@@ -25,15 +26,16 @@
.popover .popover-content .tour-counter{
  margin: 0; padding: 0;
  position: absolute;
  left: 10px; bottom: 12px;
  left: 10px; bottom: 14px;
  font-size: 11px;
  color: #acacac;
}
.popover .tour-buttons{
  padding: 8px 10px;
  min-height: 27px;
  min-height: 28px;
  background: #f5f5f5;
  border-radius: 0px 0px 6px 6px;
  box-sizing: content-box;
}
.popover .btn-close{
  background: none;
@@ -68,7 +70,8 @@
}
.qtip-tour .tour-buttons{
  padding: 8px 10px;
  min-height: 27px;
  min-height: 28px;
  background: #f5f5f5;
  border-radius: 0px 0px 6px 6px;
  box-sizing: content-box;
}
