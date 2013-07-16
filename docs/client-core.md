## gumby (responsive css framework)

```css
<div class="row">
  <div class="fourteen columns">
    <p>14 columns</p>
  </div>
</div>

<div class="row">
  <div class="twelve columns">
    <p>12 columns</p>
  </div>
  <div class="two columns">
    <p>2 columns</p>
  </div>
</div>
```

```css
<div class="medium primary btn"><a href="#">Primary</a></div>
<div class="medium secondary btn"><a href="#">Secondary</a></div>
<div class="medium default btn"><a href="#">Default</a></div>
```

```css
<div class="row">
  <ul class="ten columns">
    <li class="field">
      <label class="inline" for="text1">Label 1</label>
      <input class="wide text input" id="text1" type="text" />
    </li>

    <li class="field">
      <label class="inline" for="text2">Label 2</label>
      <input class="wide password input" id="text2" type="password" />
    </li>
  </ul>
</div>
```

## angularjs (web app framework)

```html
<!doctype html>
<html ng-app>
  <head>
    <script src="https://ajax.googleapis.com/.../angular.min.js"></script>
  </head>

  <body>
    <div>
      <label>Name:</label>
      <input type="text" ng-model="yourName" placeholder="Enter a name here">
      <hr>
      <h1>Hello {{yourName}}!</h1>
    </div>
  </body>
</html>
```
