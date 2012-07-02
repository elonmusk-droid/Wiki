Issue [#60](https://github.com/editorconfig/editorconfig/issues/60).

## Option for trimming trailing whitespace.

A `trim_trailing_whitespace` option (or similarly named option) will control whether whitespace characters preceding a newline will be removed by text editors automatically (either on file save or while editing the file).

## Naming ideas

- trim_trailing_whitespace
- trim_trailing_spaces
- allow_trailing_space


## Support in Editors

### Sublime Text 2

- By default does not show trailing whitespace. Can show all whitespace by setting `draw_white_space` to true.
- Trims trailing whitespace on save with the option `trim_trailing_white_space_on_save` set to true.

### Vim

- By default does not show trailing whitespace. To show it, turn on ['list'](http://vimdoc.sourceforge.net/htmldoc/options.html#%27list%27) option (`:set list`).
- Trimming trailing whitespace automatically or manually is possible. See [this tip](http://vim.wikia.com/wiki/Remove_unwanted_spaces).