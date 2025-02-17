### `link_list`

This option lets you specify a predefined list of links for the link dialog. These links are added to a drop-down list in the link dialog. When a list item is selected, the dialog will be populated with the relevant data. This is useful if your users need to regularly link to the same sources.

There are multiple ways to specify how to get the data for the link list, but all methods rely on the returned data containing an array of link items. A link item is an object with a `title` and a `value`. For example: `{title: 'My page 1', value: 'https://www.tiny.cloud'}`.

**Type:** `String` or `Array` or `Function`

#### Example of an array of link items

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'link',
  menubar: 'insert',
  toolbar: 'link',
  link_list: [
    {title: '{{site.companyname}} Home Page', value: '{{site.url}}'},
    {title: '{{site.companyname}} Blog', value: '{{site.url}}/blog'},
    {title: '{{site.productname}} Documentation', value: '{{site.url}}/docs/'},
    {title: '{{site.productname}} on Stack Overflow', value: '{{site.communitysupporturl}}'},
    {title: '{{site.productname}} GitHub', value: 'https://github.com/tinymce/'}
  ]
});
```

#### Example of a nested list of link items

{{site.requires_5_5v}}

To create a nested list, replace `value` with `menu` to add the top level of the list, then provide an array of items.

For example:

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'link',
  menubar: 'insert',
  toolbar: 'link',
  link_list: [
    {title: '{{site.companyname}} Home Page', value: '{{site.url}}'},
    {title: '{{site.companyname}} Blog', value: '{{site.url}}/blog'},
    {title: '{{site.productname}} Support resources',
      menu: [
        {title: '{{site.productname}} Documentation', value: '{{site.url}}/docs/'},
        {title: '{{site.productname}} on Stack Overflow', value: '{{site.communitysupporturl}}'},
        {title: '{{site.productname}} GitHub', value: 'https://github.com/tinymce/'}
      ]
    }
  ]
});
```

#### Example of an external script that returns a JSON array of link items

You can also configure a URL with JSON data. The JSON data must use the same format as above.

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'link',
  menubar: 'insert',
  toolbar: 'link',
  link_list: '/mylist.php'
});
```

#### Example of a custom asynchronous callback function

`link_list` can also take a function that is called when the link dialog is opened. {{site.productname}} passes this function a `success` callback function, which should be passed an array of link items. This allows for asynchronous and dynamic generation of the list of links.

The following is an example of how `link_list` can be used with a callback function. `fetchLinkLists` could be replaced with any function that returns an array of link items. It can be used to generate a list of link items based on:

* Data retrieved from a database.
* The current editor content.
* The current user.

```js
var fetchLinkLists = function() {
  return [
    {title: 'My page 1', value: 'https://www.tiny.cloud'},
    {title: 'My page 2', value: 'https://about.tiny.cloud'}
  ]
};

tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'link',
  menubar: 'insert',
  toolbar: 'link',
  link_list: function(success) { // called on link dialog open
    var links = fetchLinkList(); // get link_list data
    success(links); // pass link_list data to {{site.productname}}
  }
});
```

