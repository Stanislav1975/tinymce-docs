---
layout: default
title: Visual Characters plugin
title_nav: Visual Characters
description: See invisible characters like non-breaking spaces.
keywords: visualchars
controls: toolbar button, menu item
---

{% assign pluginname = "Visual Characters" %}
{% assign plugincode = "visualchars" %}

This plugin adds the ability to see invisible characters like `&nbsp;` displayed in the editable area. It also adds a toolbar control and a menu item `Show invisible characters` under the `View` menu.

## Basic setup

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'visualchars',
  menubar: 'view',
  toolbar: 'visualchars'
});
```

## Options

This setting affects the execution of the `visualchars` plugin. Characters can be configured to be visible by default using this option.

{% include configuration/visualchars_default_state.md %}

{% include misc/plugin-toolbar-button-id-boilerplate.md %}

{% include misc/plugin-menu-item-id-boilerplate.md %}

## Commands

The Visual Blocks plugin provides the following JavaScript command.

{% include commands/visualchars-cmds.md %}
