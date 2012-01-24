Version A (first stable release):

Initial property support:

* `indent_style` property can be set to "tab" or "space"
* `indent_size` property is a whole number defining number of columns used for each indentation level
* `tab_width` property defines the width of tab characters (defaults to `indent_size` when unspecified)
* `end_of_line` property can be set to "CR", "LF", or "CRLF" (case insensitive) to set line-ending style
* special `root` property can be set to `true` outside of any EditorConfig section to note current file as the top-most EditorConfig file.

Other notes on support:

* Files must be named `.editorconfig` ([instructions on creating dotfiles in Windows][dotfiles])
* Unix shell-style wildcard patterns are supported in section names: `**`, `*`, `?`, `[seq]`, and `[!seq]`
* The backslash character can be used to escape special characters in section names
* `]` character supported in section names, unlike many other INI parsers
* `;` used for line comments in EditorConfig files

[dotfiles]: http://serverfault.com/a/22628/34697