---
layout: default
title: theme_advanced_buttons_1_n
---

This option should contain a comma separated list of button/control names to insert into the toolbar. The number 1-n is the row number to insert the buttons/controls into. Below is a list of built-in controls, plugins may include other controls names that can be inserted but these are documented in the individual plugins. This option can only be used when theme is set to advanced and when the [theme_advanced_layout_manager](https://www.tiny.cloud/docs-3x/reference/configuration/Configuration3x@theme_advanced_layout_manager/) option is set to the default value of "SimpleLayout".

Since these rows have items in them by default you need to set them to empty strings "" if you want to completely remove rows. Check the example below.

You may only use `theme_advanced_buttons<1-n>` once for each value of n where `n` is a whole number starting with 1 with step 1\. If you use the same value for n more than once, the previous lines will be overwritten with the most recent declaration. It should also be noted that a button can only be used once in a TinyMCE instance, i.e. trying to put bold on rows 1 _and_ 2 will cause an error.

A complete reference of all built in buttons and controls can be found in the [button/control reference](https://www.tiny.cloud/docs-3x/reference/buttons/) page.

## Example of usage of the theme_advanced_buttons<1-n> option:

```js
tinyMCE.init({
  theme_advanced_buttons1 : "separator,insertdate,inserttime,preview,zoom,separator,forecolor,backcolor",
  theme_advanced_buttons2 : "bullist,numlist,separator,outdent,indent,separator,undo,redo,separator",
  theme_advanced_buttons3 : "hr,removeformat,visualaid,separator,sub,sup,separator,charmap"
});
```

## Example of how to remove default rows 2 and 3

```js
tinyMCE.init({
  theme_advanced_buttons1 : "bold,italic,underline",
  theme_advanced_buttons2 : "",
  theme_advanced_buttons3 : ""
});
```