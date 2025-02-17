---
layout: default
title: TinyMCE 5.9
title_nav: TinyMCE 5.9
description: Release notes for TinyMCE 5.9
keywords: releasenotes bugfixes
---

## Overview

{{site.productname}} 5.9 was released for {{site.enterpriseversion}} and {{site.cloudname}} on Wednesday, September 15<sup>th</sup>, 2021. It includes {{site.productname}} 5.9.2 and changes to premium plugins. These release notes provide an overview of the changes for {{site.productname}} 5.9, including:

- [New features](#newfeatures)
- [Enhancements](#enhancements)
- [Functionality changes](#functionalitychanges)
- [Accompanying Premium Plugin changes](#accompanyingpremiumpluginchanges)
- [Accompanying Premium Skins and Icon Packs changes](#accompanyingpremiumskinsandiconpackschanges)
- [Accompanying Premium self-hosted server-side component changes](#accompanyingpremiumself-hostedserver-sidecomponentchanges)
- [General bug fixes](#generalbugfixes)
- [Security fixes](#securityfixes)
- [Deprecated features](#deprecatedfeatures)
- [Known issues](#knownissues)
- [Upgrading to the latest version of TinyMCE 5](#upgradingtothelatestversionoftinymce5)

{{site.releasenotes_for_stable}}

## New features

The following new features were added for the {{site.productname}} 5.9 release.

### New `language` toolbar button and menu item in core

{{site.productname}} 5.9 now supports multilingual content, using the `lang` attribute. There is a new `language` toolbar button, and a new `language` menu item, both configured using the `content_langs` option. There is also a new `Lang` editor command for changing the language of the selection.

For information on:

- The `language` toolbar button, see: [Available Toolbar Buttons - The core toolbar buttons]({{site.baseurl}}/advanced/available-toolbar-buttons/#thecoretoolbarbuttons).
- The `language` menu item, see: [Available Menu Items - The core menu items]({{site.baseurl}}/advanced/available-menu-items/#thecoremenuitems).
- The `content_langs` option, see: [Content appearance options - `content_langs`]({{site.baseurl}}/configure/localization/#content_langs).
- The `Lang` editor command, see: [Commands available for {{site.productname}} - Core Editor commands]({{site.baseurl}}/advanced/editor-command-identifiers/#coreeditorcommands).

### New Table plugin features

#### New table commands

The following commands have been added to the table plugin to improve the usability:

`mceTableCellToggleClass`
: Allows the user to add or remove a class on selected cells.

`mceTableToggleClass`
: Allows the user to add or remove a class from the selected table.

`mceTableToggleCaption`
: Allows the user to add or remove a caption from the selected table.

For information on these commands, see: [Table - Commands]({{site.baseurl}}/plugins/opensource/table/#commands)

#### New table toolbar buttons and menu items

{{site.productname}} 5.9 adds new buttons and menu items for the Table plugin to improve the user experience when working with tables. The toolbar buttons and menu item use the same name (identifier). These toolbar buttons and menu items can be added to contextual menus (right-click menus) and contextual toolbars such as the table toolbar. The following toolbar buttons and menu items have been added:

`tableclass`
: Allows the user to add or remove a class from the selected table. Available classes are defined by the [`table_class_list` option]({{site.baseurl}}/plugins/opensource/table/#table_class_list).

`tablecellclass`
: Allows the user to add or remove a class from selected cells. Available classes are defined by the [`table_cell_class_list` option]({{site.baseurl}}/plugins/opensource/table/#table_cell_class_list).

`tablecellvalign`
: Allows the user to set the vertical alignment for the content of selected cells.

`tablecellborderwidth`
: Allows the user to set the border width on selected table cells. The available widths are set with the [`table_border_widths` option]({{site.baseurl}}/plugins/opensource/table/#table_border_widths).

`tablecellborderstyle`
: Allows the user to set the border style on selected table cells. The available styles are set with the [`table_border_styles` option]({{site.baseurl}}/plugins/opensource/table/#table_border_styles).

`tablecaption`
: Toggles the caption on the selected table.

`tablecellbackgroundcolor`
: Allows the user to change the background color of selected cells. The available colors are set by the [`table_background_color_map` option]({{site.baseurl}}/plugins/opensource/table/#table_background_color_map) or [`color_map` option]({{site.baseurl}}/configure/content-appearance/#color_map).

`tablecellbordercolor`
: Allows the user to change the border color of selected cells. The available colors are set by the [`table_border_color_map` option]({{site.baseurl}}/plugins/opensource/table/#table_border_color_map) or [`color_map` option]({{site.baseurl}}/configure/content-appearance/#color_map).

`tablerowheader`
: Allows the user to toggle selected rows into headers.

`tablecolheader`
: Allows the user to toggle selected columns into headers.

For information on these buttons, see: [Available toolbar buttons]({{site.baseurl}}/advanced/available-toolbar-buttons/#tableplugin)
For information on these menu items, see: [Available menu items]({{site.baseurl}}/advanced/available-menu-items/#tableplugin)

#### New table options

{{site.productname}} 5.9 adds new options for the Table plugin to improve the user experience when working with tables. These new options are optional, and allows further customization of user experience.

`table_background_color_map`
: Allows setting a specific set of background colors to be used by the `tablecellbackgroundcolor` toolbar button and menu item, overriding the defaults and the colors provided by the [`color_map` option]({{site.baseurl}}/configure/content-appearance/#color_map). For information on this option, see: [Table options - table_background_color_map]({{site.baseurl}}/plugins/opensource/table/#table_background_color_map).

`table_border_color_map`
: Allows setting a specific set of border colors to be used by the `tablecellbordercolor` toolbar button and menu item, overriding the defaults and the colors provided by the [`color_map` option]({{site.baseurl}}/configure/content-appearance/#color_map). For information on this option, see: [Table options - table_border_color_map]({{site.baseurl}}/plugins/opensource/table/#table_border_color_map).

`table_border_widths`
: Allows setting a specific set of widths to be used by the `tablecellborderwidth` toolbar button and menu item. For information on this option, see: [Table options - table_border_widths]({{site.baseurl}}/plugins/opensource/table/#table_border_widths).

`table_border_styles`
: Allows setting a specific set of HTML border styles to be used by the `tablecellborderstyle` toolbar button and menu item. For information on this option, see: [Table options - table_border_styles]({{site.baseurl}}/plugins/opensource/table/#table_border_styles).

For information on the Table plugin, see: [Table plugin]({{site.baseurl}}/plugins/opensource/table/).

### Additional new features

{{site.productname}} 5.9 introduces the following minor new features:

- Added new plugin commands:
  - `mceEmoticons` opens the Emoticons dialog.
  - `mceWordCount` displays the Word Count summary dialog.
  - `mceTemplate` shows the Template dialog.
- A new `iframe_aria_text` option for customizing the `title` attribute on the editor iframe. For details, see: [Accessibility options - `iframe_aria_text`]({{site.baseurl}}/configure/accessibility/#iframe_aria_text).
- Added a new `mceFocus` command that focuses the editor. Equivalent to using `editor.focus()`.
- Added a new `table-row-numbering` icon.
- Added a new DomParser `Node.children()` API to return all the children of a `Node`.

## Enhancements

The following enhancements were made for the {{site.productname}} 5.9 release.

### Improved context toolbar user experience

{{site.productname}} 5.9 improves context toolbar positioning by ensuring the toolbar remains in the same position when the user scrolls. Additionally, the context toolbar repositions if the toolbar will overlap the selected content or the cursor. For example: Prior to this improvement, if a user was editing a table, the context toolbar may have covered cells in the first row while it was being edited. Now, when clicking into any cell within that row, the toolbar will move to the bottom of the viewport instead.

To further enhance the user experience, the context toolbar will now use a short animation when the toolbar transitions between different locations.

![Enchanced context toolbar behavior]({{site.baseurl}}/images/context-toolbar-improvements.gif)

For information on context toolbars, see: [UI components - Context toolbar]({{site.baseurl}}/ui-components/contexttoolbar/).

### New `toolbar_sticky_offset` option for customizing sticky toolbars

The new `toolbar_sticky_offset` option allows the main toolbar to "dock" at a specified offset from the top or bottom of the view, depending on the toolbar location (set using the [`toolbar_location` option]({{site.baseurl}}/configure/editor-appearance/#toolbar_location)).

For information on the `toolbar_sticky_offset` option, see: [User interface options - toolbar_sticky_offset]({{site.baseurl}}/configure/editor-appearance/#toolbar_sticky_offset).

### Enhanced UI rendering performance

The User Interface has been profiled to find performance bottlenecks and a number of improvements have been made to increase the rendering speed. {{site.productname}} 5.9 should now be up to 20% faster at rendering the UI components, which also leads to an improved editor initialization time.

### Additional enhancements

{{site.productname}} 5.9 introduces the following minor enhancements:

- Fancy menu items now accept an `initData` property to allow custom initialization data.
- Improved the load time of the `fullpage` plugin by using the existing editor schema rather than creating a new one.
- `Env.browser` now uses the User-Agent Client Hints API where it is available.
- Icons with a `-rtl` suffix in their name will now automatically be used when the UI is rendered in right-to-left mode.
- The `formatter.match` API now accepts an optional `similar` parameter to check if the format partially matches.
- The `formatter.formatChanged` API now supports providing format variables when listening for changes.
- The formatter will now fire `FormatApply` and `FormatRemove` events for the relevant actions.
- The `autolink` plugin link detection now permits custom protocols.
- The `autolink` plugin valid link detection has been improved.

## Functionality changes

The following functionality changes were made for the {{site.productname}} 5.9 release:

- Changed the load order so content CSS is loaded before the editor is populated with content.
- Changed the `emoticons`, `wordcount`, `code`, `codesample`, and `template` plugins to open dialogs using commands.
- The context toolbar will no longer show an arrow when it overlaps the content, such as in table cells.
- The context toolbar will no longer overlap the statusbar for toolbars using `node` or `selection` positions.

## Accompanying Premium Plugin changes

The following premium plugin updates were released alongside {{site.productname}} 5.9.

### Advanced Tables 1.1.0

The {{site.productname}} 5.9 release includes an accompanying release of the **Advanced Tables** premium plugin.

**Advanced Tables** 1.1.0 provides the following new features:

This release adds row numbering functionality, allowing users to add (and remove) row numbering columns on tables. For details, see: [Advanced Tables plugin - Adding row numbering to a table]({{site.baseurl}}/plugins/premium/advtable/#addingrownumberingtoatable). This includes:

- Added a new `advtablerownumbering` toolbar button and menu item.
- Added a new `advtable_value_series` option.
- Added a new `mceTableToggleSeries` command.

For information on the Advanced Tables plugin, see: [Advanced Tables plugin]({{site.baseurl}}/plugins/premium/advtable/).

### Mentions 2.3.0

The {{site.productname}} 5.9 release includes an accompanying release of the **Mentions** premium plugin.

**Mentions** 2.3.0 adds the "profile" card feature to the `mentions_menu_hover` callback.

**Mentions** 2.3.0 also fixes the "profile" cards not displaying the `fullName` property when available.

For information on the Mentions plugin, see: [Mentions plugin]({{site.baseurl}}/plugins/premium/mentions/).

### PowerPaste 5.6.0

The {{site.productname}} 5.9 release includes an accompanying release of the **PowerPaste** premium plugin.

**PowerPaste** 5.6.0 introduces the following enhancements:

- The `powerpaste_word_import`, `powerpaste_googledocs_import`, and `powerpaste_html_import` options now also accept asynchronous functions. This allows the paste mode to be dynamically set each time a user pastes relevant content. It is designed to be used, for example, to replicate the `prompt` dialog with a custom dialog.
- More URLs can now be detected with the `smart_paste` option. Specifically, custom URL scheme detection is more accurate. For more information on URL schemes, see: [What is a URL - Scheme](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL#scheme).

**PowerPaste** 5.6.0 provides the following bug fixes:

- Word content was incorrectly parsed when copied from a German user interface.
- Paste incorrectly inserted content when the editor was in readonly mode.

For information on the PowerPaste plugin, see: [PowerPaste plugin]({{site.baseurl}}/plugins/premium/powerpaste/).

### Real-time Collaboration 1.0.1

The {{site.productname}} 5.9 release includes the first generally available cloud release of the **Real-time Collaboration (RTC)** premium plugin (version 1.0.1).

Add collaborative editing to your application and allow your content teams to edit content simultaneously and view content changes as they happen.

The RTC plugin features:

- _End-to-end encryption_ to keep content private.
- A growing list of compatible {{site.productname}} plugins and features, including: **PowerPaste**, **Tiny Drive**, **Images**, **Lists**, custom and premium **skins and icons**.
- A user presence API to assist with showing a list of connected collaborators.
- JSON Web Token based authentication.

For information on using the Real-time Collaboration (RTC) plugin, see: [Real-time Collaboration plugin]({{site.baseurl}}/rtc/).
For sales information, visit: [TinyMCE Features - Real-time Collaboration]({{site.plugindirectory}}real-time-collaboration).

### Spell Checker Pro 2.4.1

The {{site.productname}} 5.9 release includes an accompanying release of the **Spell Checker Pro** premium plugin.

**Spell Checker Pro** 2.4 (2.4.1) adds the following new features:

- The Spelling service now supports a broader range of dictionaries by introducing support for [Hunspell dictionaries](https://hunspell.github.io/), see: [New Server-side component features](#newserver-sidecomponentfeatures).
- The spellchecker dialog now supports navigating to the next and previous misspelled words.

**Spell Checker Pro** 2.4.1 includes the following changes:

- The `spellchecker_select_languages` option has been deprecated and has been replaced by the `content_langs` option, see: [The `spellchecker_select_languages` option](#thespellchecker_select_languagesoption).
- Language code validation has been moved from the client to the server.
- The Spell Checker Pro plugin has been upgraded to use version 2 of the spelling service API.
- The "Change" button text in the spellchecker dialog has been changed to "Accept".

**Spell Checker Pro** 2.4.1 introduces the following improvements:

- Improved the error messages shown in the developer console for the `SpellcheckError` event, see: [Spell Checker Pro - `Events`]({{ site.baseurl }}/plugins/premium/tinymcespellchecker/#events).

**Spell Checker Pro** 2.4.1 provides the following bug fixes:

- Links with a URL as the text content were incorrectly spellchecked.
- Resizing the editor with as-you-type mode enabled wouldn't spellcheck words that came into view.

For information on the Spell Checker Pro plugin, see: [Spell Checker Pro plugin]({{site.baseurl}}/plugins/premium/tinymcespellchecker/).

## Accompanying Premium Skins and Icon Packs changes

The {{site.productname}} 5.9 release includes an accompanying release of the **Premium Skins and Icon Packs**.

### Premium Skins and Icon Packs - New features

The following icons have been added to all premium icon packs:

- New icons for new table toolbar buttons described under [New features - New table toolbar buttons and menu items](#newtabletoolbarbuttonsandmenuitems).
- An icon for the [new Advanced Tables row numbering feature](#advancedtables110).
- A new `language` icon for the [New language toolbar button and menu item in core](#newlanguagetoolbarbuttonandmenuitemincore).

The **Bootstrap** icon pack has been updated with the latest Bootstrap icons and includes improved `table-cell-properties` and `table-row-properties` icons.

The **Material**, **Small**, and **Thin** icon packs have been updated to include improved table-cell-properties and table-row-properties icons.

For information on using premium skins and icon packs, see: [Premium Skins and Icon Packs]({{site.baseurl}}/enterprise/premium-skins-and-icon-packs/).

## Accompanying Premium self-hosted server-side component changes

The {{site.productname}} 5.9 release includes accompanying changes affecting the {{site.productname}} **self-hosted** services for the following plugins:

- The Enhanced Media Embed plugin (`mediaembed`)
- The Export plugin (`export`)
- The Image Tools plugin (`imagetools`)
- The Link Checker plugin (`linkchecker`)
- The Spell Checker Pro plugin (`tinymcespellchecker`)

The Java server-side components have been updated to the following versions:

* `ephox-spelling.war`: 2.117.3
* `ephox-hyperlinking.war`: 2.105.4
* `ephox-image-proxy.war`: 2.105.3

These versions require Java 8 or higher. For information on the removal of Java 7 support, see: [Removal of Java 7 support for TinyMCE 5.3 and later]({{site.baseurl}}/release-notes/release-notes53/#removalofjava7support).

### New Server-side component features

The Spelling service now supports a broader range of dictionaries by introducing support for [Hunspell dictionaries](https://hunspell.github.io/).

* For details on enabling Hunspell support, see: [Add Hunspell dictionaries to Spell Checker Pro]({{site.baseurl}}/enterprise/server/self-hosting-hunspell/).
* For a list of supported Spell Checker Pro languages, see: [Spell Checker Pro plugin - Supported languages]({{site.baseurl}}/plugins/premium/tinymcespellchecker/#supportedlanguages).

The Spelling service now includes a new configuration option, allowing custom dictionaries to periodically deploy changes. For details, see: [Configure server-side components: `dynamic-custom-dictionaries`]({{site.baseurl}}/enterprise/server/configure/#dynamic-custom-dictionariesoptional).

All the services now include an `ignore-port` port option to allow ports specified in `allowed-origins` to be enforced. For details, see: [Configure server-side components: `allowed-origins.ignore-port` (optional)]({{site.baseurl}}/enterprise/server/configure/#allowed-originsignore-portoptional).

For information on:

- The Spell Checker Pro plugin, see: [Spell Checker Pro plugin]({{site.baseurl}}/plugins/premium/tinymcespellchecker/).
- Deploying the server-side components, see: [Server-side component installation]({{site.baseurl}}/enterprise/server/).

### Server-side component security fixes

The server-side components (`.war` files) packaged with the {{site.productname}} 5.9 release have been updated to address various security issues.

### Stability fixes for the pre-configured server-side component Dockerfiles

The pre-configured Dockerfiles for containerizing the server-side components, also known as the Docker starter kits, have been updated to improve stability. Note that the resulting docker image will be larger as a result of these changes.

For information on deploying the server-side components using Docker, see: [Containerized service deployments]({{site.baseurl}}/enterprise/server/dockerservices/).

### Updating the self-hosted server-side components

The new versions of the server-side services provide updates for the Java-based server-side components. To deploy the updated version of the server-side components:

1. Update your Java Application Server to the minimum required version:

    - Eclipse Jetty 9.4 or later
    - Apache Tomcat:
        - 9 or later
        - 8.5.12+
        - 8.0.42+
        - 7.0.76+

2. Replace the existing server-side `.war` file with the `.war` file bundled with {{site.productname}} 5.9 or later.

For information on:

- Deploying the server-side components, see: [Server-side component installation]({{site.baseurl}}/enterprise/server/).
- Deploying the server-side components using Docker, see: [Containerized service deployments]({{site.baseurl}}/enterprise/server/dockerservices/).

## General bug fixes

{{site.productname}} 5.9 provides fixes for the following bugs:

- The `editor.fire` API was incorrectly mutating the original `args` provided.
- Unbinding an event handler did not take effect immediately while the event was firing.
- Binding an event handler incorrectly took effect immediately while the event was firing.
- Unbinding a native event handler inside the `remove` event caused an exception that blocked editor removal.
- The `SetContent` event contained the incorrect `content` when using the `editor.selection.setContent()` API.
- The editor content could be edited after calling `setProgressState(true)` in iframe mode.
- Tabbing out of the editor after calling `setProgressState(true)` behaved inconsistently in iframe mode.
- Flash of unstyled content while loading the editor because the content CSS was loaded after the editor content was rendered.
- Partially transparent RGBA values provided in the `color_map` setting were given the wrong hex value.
- HTML comments with mismatched quotes were parsed incorrectly under certain circumstances.
- The editor could crash when inserting certain HTML content.
- Links in notification text did not show the correct mouse pointer.
- Using the Tab key to navigate into the editor on Microsoft Internet Explorer 11 would incorrectly focus the toolbar.
- The editor selection could be placed in an incorrect location when undoing or redoing changes in a document containing `contenteditable="false"` elements.
- Menus and context menus were not closed when clicking into a different editor.
- Context menus on Android were not displayed when more than one HTML element was selected.
- Disabled nested menu items could still be opened.
- The nested menu item chevron icon was not fading when the menu item was disabled.
- `imagetools` buttons were incorrectly enabled for remote images without `imagetools_proxy` set.
- Only table content would be deleted when partially selecting a table and content outside the table.
- The table cell selection handling was incorrect in some cases when dealing with nested tables.
- Removing a table row or column could result in the cursor getting placed in an invalid location.
- Pressing the Tab key to navigate through table cells did not skip noneditable cells.
- Clicking on a noneditable table cell did not show a visual selection like other noneditable elements.
- Some table operations would incorrectly cause table row attributes and styles to be lost.
- The selection was incorrectly lost when using the `mceTableCellType` and `mceTableRowType` commands.
- The `mceTableRowType` was reversing the order of the rows when converting multiple header rows back to body rows.
- The table dialog did not always respect the `table_style_with_css` option.
- Pasting into a table with multiple cells selected could cause the content to be pasted in the wrong location.
- The `TableModified` event was not fired when pasting cells into a table.
- The table paste column before and after icons were not flipped in RTL mode.
- Fixed table corruption when deleting a `contenteditable="false"` cell.
- The `dir` attribute was being incorrectly applied to list items.
- Applying selector formats would sometimes not apply the format correctly to elements in a list.
- For formats that specify an attribute or style that should be removed, the formatter `match` API incorrectly returned `false`.
- The type signature on the `formatter.matchNode` API had the wrong return type (was `boolean` but should have been `Formatter | undefined`).
- The `formatter.formatChanged` API would ignore the `similar` parameter if another callback had already been registered for the same format.
- The `formatter.formatChanged` API would sometimes not run the callback the first time the format was removed.
- Base64 encoded images with spaces or line breaks in the data URI were not displayed correctly. Patch contributed by RoboBurned

## Security fixes

{{site.productname}} 5.9 provides fixes for the following security issues:

- Inserting certain HTML content into the editor could result in invalid HTML once parsed. This caused a medium severity Cross Site Scripting (XSS) vulnerability. Tiny Technologies would like to thank William Bowling for discovering this vulnerability.
- The `.war` files for the premium self-hosted server-side components have been updated to address various high and medium severity security issues.

## Deprecated features

The following features have been deprecated with the release of {{site.productname}} 5.9:

- [The `spellchecker_select_languages` option](#thespellchecker_select_languagesoption).
- [The BBCode (`bbcode`) plugin](#thebbcodebbcodeplugin)
- [The Full Page (`fullpage`) plugin](#thefullpagefullpageplugin)
- [The Legacy Output (`legacyoutput`) plugin](#thelegacyoutputlegacyoutputplugin)
- [Reminder: The free TinyMCE Spell Checker plugin](#reminderthefreetinymcespellcheckerplugin)

### The `spellchecker_select_languages` option

With the release of {{site.productname}} 5.9, the `spellchecker_select_languages` option has been deprecated and has been replaced by the `content_langs` option.

For information on the `content_langs` option, see: [Spell Checker Pro - `content_langs`]({{ site.baseurl }}/plugins/premium/tinymcespellchecker/#content_langs).

### The BBCode (`bbcode`) plugin

The BBCode plugin (`bbcode`) has been deprecated and will be removed in the 6.0 release of {{site.productname}}.

To develop and maintain a new BBCode plugin based on the {{site.productname}} BBCode plugin, you can create a fork using the [BBCode plugin source code in the TinyMCE distribution repository](https://github.com/tinymce/tinymce-dist/tree/5.8.2/plugins/bbcode).

### The Full Page (`fullpage`) plugin

The Full Page plugin (`fullpage`) has been deprecated and will be removed in the 6.0 release of {{site.productname}}.

To develop and maintain a new Full Page plugin based on the {{site.productname}} Full Page plugin, you can create a fork using the [Full Page plugin source code in the TinyMCE distribution repository](https://github.com/tinymce/tinymce-dist/tree/5.8.2/plugins/fullpage).

### The Legacy Output (`legacyoutput`) plugin

The Legacy Output plugin (`legacyoutput`) has been deprecated and will be removed in the 6.0 release of {{site.productname}}.

To develop and maintain a new Legacy Output plugin based on the {{site.productname}} Legacy Output plugin, you can create a fork using the [Legacy Output plugin source code in the TinyMCE distribution repository](https://github.com/tinymce/tinymce-dist/tree/5.8.2/plugins/legacyoutput).

### Reminder: The free TinyMCE Spell Checker plugin

The free TinyMCE Spell Checker plugin (`spellchecker`) was deprecated with the release of TinyMCE 5.4 and will be removed in the 6.0 release of {{site.productname}}.

For information on the deprecation of the free TinyMCE Spell Checker plugin, see: [TinyMCE 5.4 Release notes - Deprecated features]({{site.baseurl}}/release-notes/release-notes54/#thefreetinymcespellcheckerplugin).

## Known issues

This section describes issues that users of {{site.productname}} 5.9 may encounter and possible workarounds for these issues.

- [Core known issues](#coreknownissues)
- [Table plugin known issues](#tablepluginknownissues)
- [Real-time Collaboration (RTC) known issues](#real-timecollaborationrtcknownissues)

### Core known issues

#### "Right-hand side of 'instanceof' is not callable" or "Event is not a function. (evaluating 'e instanceof Event')" exceptions

Issue
: This issue affects developers who have overridden the native browser `Event` window object, such as those seen in some Vue.js tutorials. This breaks the native `Event` API which TinyMCE 5.9 makes use of.

Solution
: Ensure that the `Event` window or global object is not overridden in your code. The cases reported to {{site.companyname}} use something similar to `window.Event = new Vue();`. This should be renamed to something that does not conflict with a browser API, such as `window.EventBus = new Vue();`.
{{site.companyname}} highly recommends against overriding any built-in browser APIs, as the editor relies on built-in browser API behavior to function as expected.

### Table plugin known issues

#### The new table color map settings do not apply to color pickers in the table dialogs

Issue
: This issue affects the new `table_background_color_map` and `table_border_color_map` options. Setting these options will change the set of colors used in their respective toolbar buttons and menu items, but not the table dialog.

Workaround
: There was no known workaround at the time of the release.

#### Issues with the new _Table Column Header_ and _Table Row Header_ toolbar buttons and menu items

Issue
: This issue affects users of the new `tablecolheader` and `tablerowheader` toolbar buttons and menu items. Toggling off column or row headers may result in a cell being converted into a normal cell when still part of a header row or column.

Workaround
: There was no known workaround at the time of the release.

### Real-time Collaboration (RTC) known issues

#### Users are unable to add content below an Horizontal Rule (`hr`) if inserted on the last line

Issue
: If an `hr` is inserted at the end of the editor content, placing the cursor below it overwrites the `hr`.

Workaround
: There was no known workaround at the time of the release.

#### Circumstances where users are unable to clear content formatting

Issue
: The clear formatting feature only works with a selection across the text to be cleared.

Workaround
: There was no known workaround at the time of the release.

#### Possibility of inconsistent undo operations

Issue
: After adding content locally, when remote users edit that same content, local undo might not work or might remove more text than expected. This will not remove remote content.

Workaround
: There was no known workaround at the time of the release.

#### Inconsistent editor scrolling behavior when multiple users are editing various areas of a document

Issue
: When the caret is not visible, remote changes might scroll the editor to make the caret visible.

Workaround
: There was no known workaround at the time of the release.

#### Connection issues may occur when users delete large sections of content while multiple users are editing

Issue
: Deleting large sections of content (either deliberately or using undo) may result in a disconnection from the server.

Workaround
: There was no known workaround at the time of the release.

#### Errors and warnings present in the JavaScript developer console

Issue
: Several errors and warnings may be shown in the developer console (for example, opening some format menus).

Workaround
: There was no known workaround at the time of the release.

{% assign enterprise = true %}

{% include install/upgrading-info.md %}

{% assign enterprise = false %}
