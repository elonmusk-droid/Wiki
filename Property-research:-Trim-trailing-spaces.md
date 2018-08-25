Issue [#60](https://github.com/editorconfig/editorconfig/issues/60).

## Option for trimming trailing whitespace.

A `trim_trailing_whitespace` option (or similarly named option) will control whether whitespace characters preceding a newline will be removed by text editors automatically (either on file save or while editing the file).

## Naming ideas

- trim_trailing_whitespace (note: this is the name that ended up being chosen)
- trim_trailing_spaces
- allow_trailing_space
- strip_trailing_space

## Support in Editors

### Sublime Text 2

- By default does not show trailing whitespace. Can show all whitespace by setting `draw_white_space` to true.
- Trims trailing whitespace on save with the option `trim_trailing_white_space_on_save` set to true.

### Vim

- By default does not show trailing whitespace. To show it, turn on ['list'](http://vimdoc.sourceforge.net/htmldoc/options.html#%27list%27) option (`:set list`).
- Trimming trailing whitespace automatically or manually is possible. See [this tip](http://vim.wikia.com/wiki/Remove_unwanted_spaces).

### Geany

- Does not show whitespace by default. Visible whitespace can be toggled using the View > Editor > Show White Space option.
- Trims trailing whitespace on file save when the "Strip trailing spaces and tabs" option is enabled

### Notepad++

- Does not show trailing white spaces by default. Can be turned on by `View -> Show Symbol -> Show End of Line`.
- Can manually trim trailing white chars by `Edit->Blank Operations->Trim Trailing Space`.

### jEdit

- Does not show trailing white spaces by default. Viewing trailing white spaces can be turned on. Click on `Utilities` -> `Global Options...` -> `jEdit` -> `Text Area`, then check the **End of line markers** checkbox.
- Can manually trim trailing white chars by `Edit` -> `Indent` -> `Remove Trailing Whitespace`.
