---
layout: default
title: theme_advanced_fonts
---

This option should contain a semicolon separated list of font titles and font families separated by =. The titles are the ones that get presented to the user in the fonts drop down list and the font family name is the string that gets inserted into the font face or fontFamily CSS style.

## Example of usage of the theme_advanced_fonts option:

```js
tinyMCE.init({
	...
	theme_advanced_fonts : "Arial=arial,helvetica,sans-serif;Courier New=courier new,courier,monospace;AkrutiKndPadmini=Akpdmi-n"
});
```

The default value is:

```js
tinyMCE.init({
	...
	theme_advanced_fonts : "Andale Mono=andale mono,times;"+
		"Arial=arial,helvetica,sans-serif;"+
		"Arial Black=arial black,avant garde;"+
		"Book Antiqua=book antiqua,palatino;"+
		"Comic Sans MS=comic sans ms,sans-serif;"+
		"Courier New=courier new,courier;"+
		"Georgia=georgia,palatino;"+
		"Helvetica=helvetica;"+
		"Impact=impact,chicago;"+
		"Symbol=symbol;"+
		"Tahoma=tahoma,arial,helvetica,sans-serif;"+
		"Terminal=terminal,monaco;"+
		"Times New Roman=times new roman,times;"+
		"Trebuchet MS=trebuchet ms,geneva;"+
		"Verdana=verdana,geneva;"+
		"Webdings=webdings;"+
		"Wingdings=wingdings,zapf dingbats",
	...
});
```