### `table_clone_elements`

This option enables you to specify which elements should be cloned as empty children when inserting rows/columns to a table. By default it will clone these '`strong` `em` `b` `i` `span` `font` `h1` `h2` `h3` `h4` `h5` `h6` `p` `div`' into new cells.

**Type:** `String`

#### Example: Using `table_clone_elements`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'table',
  table_clone_elements: 'strong em a'
});
```

