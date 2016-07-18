---
layout: default
title: valid_child_elements
---

**This option has been replaced with the new [valid_children](../configuration/Configuration3x@valid_children) as of 3.4.**

This option gives you the ability to specify what elements are valid inside different parent elements. For example you may force that only thead,tbody,tfoot are valid within a table element. This option gives you a lot more control of the output XHTML and to ensure that it is more valid according to W3C specifications.

## Format:

| Name | Summary |
| --- | --- |
| / | Separates elements. Multiple elements may match a set of child nodes. |
| , | Separates element chunks. |
| | | Separates child element names. |
| [ | Starts a new child node list for a element definition. |
| ] | Ends a new child node list for a element definition. |
| %itrans | Variable for inline XHTML transitional elements. |
| %itrans_na | Variable for inline XHTML transitional elements excluding A elements. |
| %btrans | Variable for block XHTML transitional elements. |
| %istrict | Variable for inline XHTML strict elements. |
| %istrict_na | Variable for inline XHTML strict elements excluding A elements. |
| %bstrict | Variable for block XHTML strict elements. |
| #text | Name for text nodes. |
| #comment | Name for comment nodes. |

## Example of usage of the valid_child_elements option:

```html
tinyMCE.init({
	...
	valid_child_elements : "h1/h2/h3/h4/h5/h6/a[%itrans_na],table[thead|tbody|tfoot|tr|td],strong/b/p/div/em/i/td[%itrans|#text],body[%btrans|#text]"
});
```