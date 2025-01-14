### `template_selected_content_classes`

When HTML elements in a template are assigned this class, the content of the element will be replaced with selected content from the editor. This option accepts a list of classes (separated by spaces).

**Type:** `String`

**Default Value:** `selcontent`

#### Example: Using `template_selected_content_classes`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'template',
  template_selected_content_classes: 'selcontent selectedcontent',
  templates: [
    {
      title: 'My Template',
      description: 'This is my template.',
      content: '<p>Hello, <span class="selcontent">this statement will be replaced.</span></p>'
    }
  ]
});
```

If the word `world` is selected in the editor and _My Template_ is applied, `world` will be updated to:

```html
<p>Hello, <span class="selcontent">world</span></p>
```

