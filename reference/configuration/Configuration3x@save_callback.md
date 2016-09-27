---
layout: default
title: save_callback
---

This option is considered deprecated. Use the new [Event API](https://www.tinymce.com/docs-3x/api/class_tinymce.Editor.html/)

This option enables you to add custom logic to be executed when the contents are extracted/saved. This custom logic can then modify the contents before it's submitted to a serverside page. This can be useful if you want to do your own regexp cleanups and so forth. The format of this function is: `saveContent(element_id, html, body)`. Where `element_id` is the form element/div id of the editor and HTML is the HTML contents after the built-in cleanup process has executed. This function should return the new HTML contents.

## Example of usage of the save_callback option:

```js
function myCustomSaveContent(element_id, html, body) {
  // Do some custom HTML cleanup
  html = html.replace(/a/g,'b');

  return html;
}

tinyMCE.init({
  save_callback : "myCustomSaveContent"
});
```