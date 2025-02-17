### `table_responsive_width`

> **Note**: This option was deprecated with the release of {{site.productname}} 5.4. This option has been replaced by [`table_sizing_mode`](#table_sizing_mode). This option will be removed in {{site.productname}} 6.0.

This option enables you to force pixels or percentage sizes for tables. Setting this to true will force resizing by percentages and setting this to false
will force pixel resizing. The default is to automatically detect what the table size is and just use that unit for resizing.

**Type:** `Boolean`

#### Example: Using `table_responsive_width`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'table',
  menubar: 'table',
  toolbar: 'table',
  table_responsive_width: false
});
```
