---
layout: default
title: Load/Save with Ajax in TinyMCE
---

Saving and loading data with TinyMCE and Ajax is fairly simple.

Here is a simple example that you should be able to follow.

```js
<script type="text/javascript" src="<your installation path>/tiny_mce/tiny_mce.js"></script>
<script type="text/javascript">
tinyMCE.init({
    mode : "textareas",
    theme : "advanced"
});

function ajaxLoad() {
    var ed = tinyMCE.get('content');

    // Do you ajax call here, window.setTimeout fakes ajax call
    ed.setProgressState(1); // Show progress
    window.setTimeout(function() {
        ed.setProgressState(0); // Hide progress
        ed.setContent('HTML content that got passed from server.');
    }, 3000);
}

function ajaxSave() {
    var ed = tinyMCE.get('content');

    // Do you ajax call here, window.setTimeout fakes ajax call
    ed.setProgressState(1); // Show progress
    window.setTimeout(function() {
        ed.setProgressState(0); // Hide progress
        alert(ed.getContent());
    }, 3000);
}
</script>

<form method="post" action="somepage">
    <textarea name="content" style="width:100%">
    </textarea>
</form>
```

It is as simple as that, to simplify loading/saving use some form of Ajax lib or jQuery for example.