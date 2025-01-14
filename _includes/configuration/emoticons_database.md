### `emoticons_database`

{{ site.requires_5_6v }}

This option provides the ability to specify which built-in emoji database to use when rendering emojis in the editor. The following built-in emoji databases are available:
* `emojis` - This database uses Unicode characters to represent emoji in the editor content.
* `emojiimages` - This database uses images provided by the Twitter Emoji (twemoji) project to represent emoji in the editor content.

{% assign feature = "`emojiimages` database" %}
{% assign third_party_product = "Twitter Emoji (twemoji) graphics" %}
{% assign license_agreement_name = "CC-BY 4.0" %}
{% include misc/under-license.md %}

**Type:** `String`

**Default:** `emojis`

#### Example: Using `emoticons_database`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'emoticons',
  toolbar: 'emoticons',
  emoticons_database: 'emojis'
});
```
