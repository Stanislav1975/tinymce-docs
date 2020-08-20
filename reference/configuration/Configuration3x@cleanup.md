---
layout: default
title: cleanup
---

**Removed in 3.4**

This option enables or disables the built-in clean up functionality. TinyMCE is equipped with powerful clean up functionality that enables you to specify what elements and attributes are allowed and how HTML contents should be generated. This option is set to true by default, but if you want to disable it you may set it to false.

Notice: It's not recommended to disable this feature.

It might be worth mentioning that the browser usually messes with the HTML. The clean up not only fixes several problems with the browsers' parsed HTML document, like paths etc., it also makes sure it is a correct XHTML document, with all tags closed, the " at the right places, and things like that.

Example of usage of the cleanup option:

```js
tinyMCE.init({
  cleanup : true
});
```