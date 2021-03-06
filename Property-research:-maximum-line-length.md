This page includes research for two options discussed in issue [#89](https://github.com/editorconfig/editorconfig/issues/89).

## Option for displaying a vertical rules

A new option will force editors to show a vertical rules at certain column(s).  

## Option for setting a maximum length for each line

A `max_line_length` option (or similarly named option) will force either hard or soft line wrapping after the amount of characters specified.  

## Behavior

1. The editor should display vertical rulers at the given rulers columns.
2. When typing, the editor automatically wraps the current word to a new line if it reaches the given limit.

## Naming ideas

For the first item:

- rulers
- line_width

For the second item:

- text_width
- line_width
- wrap_width
- max_line_length
- right_margin

## Concerns

- How should line length be set when tabs are used?
- Should line be wrapped immediately once length is hit or once line is left/Enter is pressed?
- Should this be disable-able by the user in case they want to control this manually?


## Support in Editors

### Sublime Text 2

The setting is `wrap_width`.

The `rulers` setting allows you to provide an array of column numbers at which a vertical ruler will be displayed.

### Vim

The setting is `textwidth`.

```
Maximum width of text that is being inserted.  A longer line will be
broken after white space to get this width.  A zero value disables
this. 'textwidth' is set to 0 when the 'paste' option is set.  When
'textwidth' is zero, 'wrapmargin' may be used. See also
'formatoptions' and ins-textwidth.
When 'formatexpr' is set it will be used to break the line.
NOTE: This option is set to 0 when 'compatible' is set.
```

The setting `colorcolumn` just displays a vertical line but doesn't enforce the width.

```
'colorcolumn' is a comma separated list of screen columns that are
highlighted with ColorColumn hl-ColorColumn.  Useful to align
text.  Will make screen redrawing slower.
The screen column can be an absolute number, or a number preceded with
'+' or '-', which is added to or subtracted from 'textwidth'.
```

### Emacs

- Variable `fill-column`: "Column beyond which automatic line-wrapping should happen."
- Used by `M-x fill-paragraph` and `auto-fill-mode` among others.
- The `auto-fill-mode` minor mode wraps long lines automatically when the user types a newline. It's possible for a script to enable `auto-fill-mode` on the user's behalf, but IIRC this is frowned upon in the Emacs community.
- Although not included in Emacs itself, there is also the [fill-column-indicator](https://www.emacswiki.org/emacs/FillColumnIndicator) package in ELPA and Debian.

### Geany

* Document, Line Breaking: enables line breaking at boundary.
* Edit, Preferences, Editor, Features, Line breaking column: sets where the boundary is
* Edit, Preferences, Editor, Display, Column: sets at what column a vertical line indicator should be

### Notepad++

Not possible. Can be manually done by TextFX plugin to rewrap selected text. ( **TextFX** -> **TextFX Edit** -> **ReWrap Text to (72 or clipboard) width** )

### Gedit

Has a "Display right margin at column:" preference to display what width we want the text to be. It doesn't support a mode to enforce that width though. Maybe trough plugins.

### jEdit

Set `maxLineLen` to the line max width, and `wrap` to **hard** for real line break. See these buffer local properties [here](http://www.jedit.org/users-guide/buffer-local.html).

### Code::Blocks

Not possible.

Settings, Editor, Margins and caret, right margin hint: visible line & hint column

### TextMate

TODO

### Visual Studio

TODO

### Visual Studio Code

Set a value (e.g., 100) in "editor.rulers": [ 100 ]