### `spellchecker_languages`

This option specifies the spellchecker languages that are available to the user, provided as a comma delimited string. For a list of available languages, see: [Supported languages](#supportedlanguages).

**Type:** comma-separated `String`

**Default Value:**
```
'English (United States)=en_US,English (United Kingdom)=en_GB,Danish=da,Dutch=nl,Finnish=fi,French=fr,German=de,Italian=it,Norwegian=nb,Portuguese=pt,Portuguese (Portugal)=pt_PT,Spanish=es,Swedish=sv'
```

#### Example: Using `spellchecker_languages`

```js
tinymce.init({
  selector: 'textarea',
  plugins: 'tinymcespellchecker',
  spellchecker_languages: 'US English=en_US,UK English=en_GB,Danish=da,Dutch=nl,Finnish=fi,French=fr,German=de,Italian=it,Norwegian=nb,Brazilian Portuguese=pt,Iberian Portuguese=pt_PT,Spanish=es,Swedish=sv'
});
```

