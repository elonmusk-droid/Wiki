# How to Create an EditorConfig Plugin

We want every text editor and IDE to understand `.editorconfig` files.  This document is a guide for EditorConfig plugin developers (or aspiring plugin developers).  If you want to make a plugin for your text editor, please read this document and consider the below suggestions while developing your plugin.


## Creating a Plugin for your Editor

The first step when creating a plugin is to figure out *how* to create plugins for your editor.  Search the [mailing list][] and [issue tracker][] for your editor to see if someone else has researched it before.  Also try searching the Internet for **<your editor> plugin how to**.

### Note which Core Library to Use

The most important detail to note first is what programming language your plugin will need to be written in.  This will help you determine which EditorConfig core library you should use for writing your plugin.  For example Eclipse plugins are written in Java so the Java core library should be used for Eclipse plugins.  The current EditorConfig core libraries are the [Python core][], the [Java core][], and the [C core][].

After you determine which core library you should use, consult the plugin API to determine which EditorConfig properties your editor will be able to support.  Is there an option for setting indentation to tabs or spaces?  Is there an option for setting indentation size?  What about for setting specifically the width of a tab character?

### Start a Discussion

If you've done some research on your text editor and want to share what you've found or announce your efforts to create a plugin, start a discussion on the [mailing list][].  If you are having trouble getting started, feel free to ask for help on the mailing list as well.

### Inadequate API Support for EditorConfig properties

If your editor's plugin API does not appear to support EditorConfig properties, you might consider contacting the developers of your editor.  Sometimes even text editors with incomplete (or non-existant) APIs can still be extended to support EditorConfig.  Many text editor and IDE developers are quite responsive to plugin developers looking to extend their product (it helps to ask nicely also).

### Handling Unsupported EditorConfig properties

If your plugin won't be able to fully support some EditorConfig properties, just note the level of support in the README file.  Some support is better than none at all.

The Gedit plugin only partially supports the `indent_size` and `tab_width` properties.  This is because there is no option in the Gedit plugin API to set the size of a tab character (tabs are assumed to always be the same as the indentation size).  This is noted in the [README file for the Gedit plugin][Gedit supported properties].

## Using the EditorConfig core libraries

The EditorConfig core libraries take as input a filepath and returns the EditorConfig properties that match the given filepath.  An EditorConfig plugin should use these properties to change text editor settings when editing that file.

### Unknown/invalid properties or property values should be ignored

When an unknown EditorConfig property is encountered, it should be ignored.  This allows future EditorConfig properties to be added without breaking backwards compatibility and it allows custom properties for domain-specific applications.

When a known EditorConfig property has an unknown or invalid value, it should be ignored.  For example if `indent_size = N/A` is set, this should be equivalent to `indent_size` being unspecified.  This allows existing properties to be extended in the future.  It also allows property values to be reset to their default, as if they were unspecified.

When a particular valid EditorConfig property cannot be properly handled appropriately, it should be ignored in a reasonable manner.  For example if `indent_size = 11` and the editor does not support an indentation size of 11 the indentation size should not be changed.

### Handling errors

When an error occurs while retrieving EditorConfig properties it is probably best **not** to notify the user in an intrusive way.  An error log may be useful for debugging if the user finds they need to hunt down an improper `.editorconfig` file.  A setting that allows the user to be alerted by debugging or error messages could also be useful.

## Testing your plugin

The [EditorConfig Plugin Tests][] repository contains a set of tests for confirming that your plugin behaves correctly when handling various EditorConfig properties.  This set of tests is not comprehensive, but it's a good starting point.

## Releasing your plugin

Many of the plugins are hosted in a similar fashion so they can be compared easily.  The majority of the plugins are hosted on Github, the README files are often similar, many plugins share an issue tracker, and many use the same open source licenses.

### Licensing

Most EditorConfig plugins are licensed under the [Simplified BSD][] license.  Some exceptions to this are the Notepad++ plugin which is under the [GNU General Public License][GPL] and the Sublime Text 2 plugin which is under an [MIT License][].

You can host your plugin under any license you like (just make sure the license is clear and that it does not conflict with any other licenses that may be used in your plugin source tree).

### Hosting

When releasing your plugin you have two options for hosting your plugin:

1. Request that your plugin be hosted in the EditorConfig Github organization (where many of the other plugins reside)
2. Host your plugin yourself (on Github or elsewhere)

We usually use the [main EditorConfig issue tracker][issue tracker] for all plugins hosted in the EditorConfig Github organization.

### The README file

Most of our README files use a similar format.  You may copy this format or use your own.  Make sure to note EditorConfig properties that your plugin currently supports and link to the relevant issue tracker for your plugin.

[mailing list]: http://groups.google.com/group/editorconfig
[issue tracker]: https://github.com/editorconfig/editorconfig/issues
[Gedit supported properties]: https://github.com/editorconfig/editorconfig-gedit#supported-properties
[Python core]: https://github.com/editorconfig/editorconfig-core-py#readme
[Java core]: https://github.com/editorconfig/editorconfig-core-py/tree/master/java-binding#readme
[C core]: https://github.com/editorconfig/editorconfig-core#readme
[Simplified BSD]: http://www.opensource.org/licenses/BSD-2-Clause
[GPL]: http://www.opensource.org/licenses/gpl-license
[MIT License]: http://www.opensource.org/licenses/MIT
[editorconfig plugin tests]: https://github.com/editorconfig/editorconfig-plugin-tests