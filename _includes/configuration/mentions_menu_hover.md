### `mentions_menu_hover`

This option enables you to provide an element to present next to the menu item being hovered. This lets you do custom UIs for presenting user information.

**Type:** `Function`

#### Example: Using `mentions_menu_hover`

```js
var userRequest = {};
tinymce.init({
  selector: 'textarea',
  plugins: 'mentions',
  mentions_menu_hover: function (userInfo, success) {
    // request more information about the user from the server and cache it locally
    if (!userRequest[userInfo.id]) {
      userRequest[userInfo.id] = fetch('/user?id=' + userInfo.id);
    }
    userRequest[userInfo.id].then(function(userDetail) {
      var div = document.createElement('div');

      div.innerHTML = (
      '<div>' +
        '<h1>' + userDetail.fullName + '</h1>' +
        '<img src="' + userDetail.image + '" ' +
            'style="width: 50px; height: 50px; float: left;"/>' +
        '<p>' + userDetail.description + '</p>' +
      '</div>'
      );

      success(div);
    });
  }
});
```

#### `mentions_menu_hover` with predefined templates

{{site.requires_5_9v}}

If `mentions_menu_hover` is resolved with an object specifying the type and user details, a predefined hover card template will be used. To use the predefined template, set `type` to `'profile'`. For details on the user properties required for the `profile` template, see: [User properties](#userproperties).

##### Example: Using the `'profile'` template with `mentions_menu_hover`

```js
var userRequest = {};
tinymce.init({
  selector: 'textarea',
  plugins: 'mentions',
  mentions_menu_hover: function (userInfo, success) {
    // request more information about the user from the server and cache it locally
    if (!userRequest[userInfo.id]) {
      userRequest[userInfo.id] = fetch('/user?id=' + userInfo.id);
    }
    userRequest[userInfo.id].then(function(userDetail) {
      success({ type: 'profile', user: userDetail });
    });
  }
});
```