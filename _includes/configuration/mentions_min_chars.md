### `mentions_min_chars`

{{site.requires_5_6v}}

This option specifies the number of characters a user needs to type after the "@" symbol before the list of users will be displayed.

**Type:** `Number`

**Default Value:** `1`

#### Example: Using `mentions_min_chars`

```js
tinymce.init({
  selector: 'textarea',
  plugins: 'mentions',
  mentions_min_chars: 1
});
```
