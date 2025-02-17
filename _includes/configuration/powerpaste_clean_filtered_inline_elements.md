### `powerpaste_clean_filtered_inline_elements`

This option allows for configuration of PowerPaste's **"clean"** paste filters for inline elements. These filters are run when `powerpaste_word_import` or `powerpaste_html_import` are set to `"clean"`; or when a user clicks the **"Remove formatting"** button on the paste prompt dialog.

The list of inline elements that should be removed on paste can be specified by setting `powerpaste_clean_filtered_inline_elements` to a comma-separated string of inline element tag names.

**Possible Values:**  A comma-separated string.

#### Example: `powerpaste_clean_filtered_inline_elements`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'powerpaste',
  powerpaste_word_import: 'clean', // optional
  powerpaste_html_import: 'clean', // optional
  powerpaste_clean_filtered_inline_elements: 'strong, em, b, i, u, strike, sup, sub, font'
});
```
