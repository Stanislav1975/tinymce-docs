---
layout: default
title: Template plugin
title_nav: Template
description: Custom templates for your content.
keywords: insert template_cdate_classes template_cdate_format template_mdate_classes template_mdate_format  template_replace_values template_selected_content_classes template_preview_replace_values
controls: toolbar button, menu item
---

{% assign pluginname = "Template" %}
{% assign plugincode = "template" %}

The `template` plugin adds support for custom templates. It also adds a menu item `Insert template` under the `Insert` menu and a toolbar button.

## Basic setup

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'template',
  menubar: 'insert',
  toolbar: 'template'
});
```

## Interactive example

This example shows how the template plugin can be used to insert custom templates with pre-defined markup and values.

{% include live-demo.html id="template" tab="js" %}

## Configuration Options

These settings affect the execution of the `template` plugin. Predefined templates for items such as created dates and modified dates can be set here.

{% include configuration/templates.md %}

{% include configuration/template_cdate_classes.md %}

{% include configuration/template_cdate_format.md %}

{% include configuration/template_mdate_classes.md %}

{% include configuration/template_mdate_format.md %}

{% include configuration/template_replace_values.md %}

{% include configuration/template_preview_replace_values.md %}

{% include configuration/template_selected_content_classes.md %}

## Template Plugin Examples

### Example: Using the `template` plugin

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'template',
  menubar: 'insert',
  toolbar: 'template',
  template_cdate_classes: 'cdate creationdate',
  template_mdate_classes: 'mdate modifieddate',
  template_selected_content_classes: 'selcontent',
  template_cdate_format: '%m/%d/%Y : %H:%M:%S',
  template_mdate_format: '%m/%d/%Y : %H:%M:%S',
  template_replace_values: {
    username : 'Jack Black',
    staffid : '991234'
  },
  templates : [
    {
      title: 'Editor Details',
      url: 'editor_details.htm',
      description: 'Adds Editor Name and Staff ID'
    },
      {
        title: 'Timestamp',
        url: 'time.htm',
        description: 'Adds an editing timestamp.'
      }
  ]
});
```

### Example of an external template list

This is the contents your backend page should return if you specify a URL in the templates option. A simple array containing each template to present. This URL can be a backend page, for example a PHP file.

```json
[
  {"title": "Some title 1", "description": "Some desc 1", "content": "My content"},
  {"title": "Some title 2", "description": "Some desc 2", "url": "development.html"}
]
```

## Making Templates

A template is a file with a `div` containing the template data. All `html` outside the `div` will simply be presented to the user in the preview frame.

A template has more capabilities than a simple snippet, for example, a template can have dynamic content/smart content that gets updated by functions located in the `template_replace_values` key. These functions will continue to be executed each time a cleanup procedure is performed.

Each template needs to be inside of a div with the `mceTmpl` class, like this example:

```html
<!-- This will not be inserted -->
<div class="mceTmpl">
  <table width="98%%"  border="0" cellspacing="0" cellpadding="0">
    <tr>
      <th scope="col"> </th>
      <th scope="col"> </th>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
    </tr>
  </table>
</div>
```

## Making Snippets

Snippets are `html` code chunks that can be inserted. Replace variables will only be executed upon insert, without being wrapped in a template `div` element. So if you define `somevar1` in `template_replace_values` array it will be replaced on insert. If you wish to preview the replacements before inserting, use `template_preview_replace_values`.

```html
This is a simple <strong>snippet</strong>. Will be replaced: {$somevar1}.
```

{% include configuration/ref_time_date_formats.md %}

{% include misc/plugin-toolbar-button-id-boilerplate.md %}

{% include misc/plugin-menu-item-id-boilerplate.md %}

## Commands

The Template plugin provides the following JavaScript command.

{% include commands/template-cmds.md %}
