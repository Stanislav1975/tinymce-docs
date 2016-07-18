---
layout: default
title: Creating a theme
---

Creating your own themes for the TinyMCE application is fairly easy if you know the basics of HTML, CSS and Javascript. The easiest way is to copy the "simple" or the "advanced" template and rename it ("mytheme", for example). After you copy the template, you need to change the red sections marked below to "mytheme". This is needed so that themes don't conflict; in other words, it gives the theme a unique name. Then just alter the HTML code as you see fit, but notice some elements need to be there, so check the documents below about each function. Also remember that your custom theme needs to be located in TinyMCE's "themes" directory.

## Theme options

If you want you may add theme specific options and settings, but remember to prefix them in the following format in order to provide a unique name space: "<your theme>_<option>" ("mytheme_someoption", for example). Use [tinyMCE.getParam](/wiki.php/API3:method.tinymce.Editor.getParam) to retrieve a custom theme option value.

## Theme directory structure

| Path | Summary |
| --- | --- |
| /css | Theme specific CSS files |
| /docs | Theme specific documentation |
| /images | Theme specific images |
| /jscripts | Theme specific JavaScript for HTML dialogs |
| /langs | Theme specific language files |
| /editor_template.js | Editor theme template file (compressed). |
| /editor_template_src.js | Editor theme template file (source). |
| /somedialog.htm | Theme specific dialog HTML file. |

## Theme example source

The example below shows a simple empty theme and all possible callbacks.

Please note that you need to replace "SomeName" with your own theme name.

```html
var TinyMCE_SomeNameTheme = {
	/**
	 * Returns information about the theme as a name/value array.
	 * The current keys are longname, author, authorurl, infourl and version.
	 *
	 * @returns Name/value array containing information about the theme.
	 * @type Array 
	 */
	getInfo : function() {
		return {
			longname : 'Your Theme',
			author : 'Your name',
			authorurl : 'http://www.yoursite.com',
			infourl : 'http://www.yoursite.com/docs/template.html',
			version : "1.0"
		};
	},

	/**
	 * Gets executed when a TinyMCE editor instance is initialized.
	 *
	 * @param {TinyMCE_Control} Initialized TinyMCE editor control instance. 
	 */
	initInstance : function(inst) {
		// You can take out theme specific parameters
		alert("Initialization parameter:" + tinyMCE.getParam("somename_someparam", false));

		// Register custom keyboard shortcut
		inst.addShortcut('ctrl', 't', 'lang_somename_desc', 'mceSomeCommand');
	},

	/**
	 * Gets executed when a TinyMCE editor instance is displayed using for example mceToggleEditor command.
	 *
	 * @param {TinyMCE_Control} Visible TinyMCE editor control instance. 
	 */
	showInstance : function(inst) {
		// Show instance resources
	},

	/**
	 * Gets executed when a TinyMCE editor instance is hidden using for example mceToggleEditor command.
	 *
	 * @param {TinyMCE_Control} Hidden TinyMCE editor control instance. 
	 */
	hideInstance : function(inst) {
		// Hide instance resources
	},

	/**
	 * Gets executed when a TinyMCE editor instance is removed.
	 *
	 * @param {TinyMCE_Control} Removed TinyMCE editor control instance. 
	 */
	removeInstance : function(inst) {
		// Cleanup instance resources
	},

	/**
	 * Returns the HTML code for a specific control or empty string if this theme doesn't have that control.
	 * A control can be a button, select list or any other HTML item to present in the TinyMCE user interface.
	 * The variable {$editor_id} will be replaced with the current editor instance id and {$themeurl} will be replaced
	 * with the URL of the theme. Language variables such as {$lang_somekey} will also be replaced with contents from
	 * the language packs.
	 *
	 * @param {string} cn Editor control/button name to get HTML for.
	 * @return HTML code for a specific control or empty string.
	 * @type string
	 */
	getControlHTML : function(cn) {
		switch (cn) {
			case "SomeControl":
				return tinyMCE.getButtonHTML(cn, 'lang_sometheme_button_desc', '{$themeurl}/images/someimage.gif', 'mceSomeCommand');
		}

		return "";
	},

	/**
	 * Returns the HTML code that should be inserted for a specific editor instance.
	 * This function should return a name/value array with three items html, delta_width, delta_height.
	 * The html item should contain the HTML code to insert as a editor instance.
	 * The variable {$editor_id} will be replaced with the current editor instance id and {$themeurl} will be replaced
	 * with the URL of the theme. Language variables such as {$lang_somekey} will also be replaced with contents from
	 * the language packs. Any element with the id {$editor_id} will be replaced with the editor iframe element.
	 * The {$width} and {$height} variables will be replaced with the editors outside dimension values.
	 * The delta_width/height is the relative width/height in pixels to add or remove from the iframe dimensions.
	 *
	 * @param {Array} settings Name/Value array instance settings.
	 * @param {string} editor_id TinMYCE editor control instance id.
	 * @return Name/Value array of editor template data.
	 * @type Array
	 */
	getEditorTemplate : function(settings, editor_id) {
		var html = "";

		// Build toolbar and editor instance
		html += "..";

		return {
			html : html,
			delta_width : 0,
			delta_height : 0
		};
	},

	/**
	 * Executes a specific command, this function handles theme commands.
	 *
	 * @param {string} editor_id TinyMCE editor instance id that issued the command.
	 * @param {HTMLElement} element Body or root element for the editor instance.
	 * @param {string} command Command name to be executed.
	 * @param {string} user_interface True/false if a user interface should be presented.
	 * @param {mixed} value Custom value argument, can be anything.
	 * @return true/false if the command was executed by this theme or not.
	 * @type
	 */
	execCommand : function(editor_id, element, command, user_interface, value) {
		// Handle commands
		switch (command) {
			// Remember to have the "mce" prefix for commands so they don't intersect with built in ones in the browser.
			case "mceSomeCommand":
				// Do your custom command logic here.

				return true;
		}

		// Pass to next handler in chain
		return false;
	},

	/**
	 * Gets called ones the cursor/selection in a TinyMCE instance changes. This is useful to enable/disable
	 * button controls depending on where the user are and what they have selected. This method gets executed
	 * alot and should be as performance tuned as possible.
	 *
	 * @param {string} editor_id TinyMCE editor instance id that was changed.
	 * @param {HTMLNode} node Current node location, where the cursor is in the DOM tree.
	 * @param {int} undo_index The current undo index, if this is -1 custom undo/redo is disabled.
	 * @param {int} undo_levels The current undo levels, if this is -1 custom undo/redo is disabled.
	 * @param {boolean} visual_aid Is visual aids enabled/disabled ex: dotted lines on tables.
	 * @param {boolean} any_selection Is there any selection at all or is there only a cursor.
	 */
	handleNodeChange : function(editor_id, node, undo_index, undo_levels, visual_aid, any_selection) {
	},

	/**
	 * Gets called when a TinyMCE editor instance gets filled with content on startup.
	 *
	 * @param {string} editor_id TinyMCE editor instance id that was filled with content.
	 * @param {HTMLElement} body HTML body element of editor instance.
	 * @param {HTMLDocument} doc HTML document instance.
	 */
	setupContent : function(editor_id, body, doc) {
	},

	/**
	 * Gets called when the contents of a TinyMCE area is modified, in other words when a undo level is
	 * added.
	 *
	 * @param {TinyMCE_Control} inst TinyMCE editor area control instance that got modified.
	 */
	onChange : function(inst) {
	},

	/**
	 * Gets called when TinyMCE handles events such as keydown, mousedown etc. TinyMCE
	 * doesn't listen on all types of events so custom event handling may be required for
	 * some purposes.
	 *
	 * @param {Event} e HTML editor event reference.
	 * @return true - pass to next handler in chain, false - stop chain execution
	 * @type boolean
	 */
	handleEvent : function(e) {
		return true;
	},

	/**
	 * Gets called when HTML contents is inserted or retrived from a TinyMCE editor instance.
	 * The type parameter contains what type of event that was performed and what format the content is in.
	 * Possible valuses for type is get_from_editor, insert_to_editor, get_from_editor_dom, insert_to_editor_dom.
	 *
	 * @param {string} type Cleanup event type.
	 * @param {mixed} content Editor contents that gets inserted/extracted can be a string or DOM element.
	 * @param {TinyMCE_Control} inst TinyMCE editor instance control that performes the cleanup.
	 * @return New content or the input content depending on action.
	 * @type string
	 */
	cleanup : function(type, content, inst) {
		return content;
	},

	// Private theme internal methods

	/**
	 * This is just a internal theme method, prefix all internal methods with a _ character.
	 * The prefix is needed so they doesn't collide with future TinyMCE callback functions.
	 *
	 * @param {string} a Some arg1.
	 * @param {string} b Some arg2.
	 * @return Some return.
	 * @type string
	 */
	_someInternalFunction : function(a, b) {
		return 1;
	}
};

// Adds the theme class to the list of available TinyMCE themes
tinyMCE.addTheme("sometheme", TinyMCE_SomeThemeTheme);

```

## Creating popup HTML files

When creating a popup you need to include the "tiny_mce_popup.js" this enables you to retrive the tinyMCE global instance in all popup windows. All variables and language definitions gets replaced in the page when it loads. So language variables such as {$lang_something} can be places in the HTML code, if you need to get a language string in JavaScript simply use the tinyMCE.getLang function.

## Example of simple popup file

```html
<html>
<head>
<title>{$lang_theme_sample_title}</title>
<script language="javascript" src="../../tiny_mce_popup.js"></script>
<script language="javascript">
     // getWindowArg returns any arguments passed to the window
     alert(tinyMCE.getWindowArg('some_arg'));
</script>
<body>
     <strong>{$lang_theme_sample_desc}</strong>
</body>

```

## Troubleshooting

One thing to note when creating a new theme is that this theme cannot share the same name as a plugin to TinyMCE. It is possible that functions may conflict with one another.