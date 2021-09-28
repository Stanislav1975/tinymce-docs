### `table_default_attributes`

This option enables you to specify default attributes for inserted tables.

**Type:** `Object`

**Default Value:** `{ border: '1' }`

#### Example: Using `table_default_attributes`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'table',
  menubar: 'table',
  toolbar: 'table',
  table_default_attributes: {
    border: '1'
  }
});
```