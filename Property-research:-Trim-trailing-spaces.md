Issue [#60](https://github.com/editorconfig/editorconfig/issues/60).

Option for trimming trailing whitespace.


## Naming ideas

- trim_trailing_whitespace
- allow_trailing_space


## Support in Editors

### Sublime Text 2

- Does not show trailing whitespace.
- Trims trailing whitespace on save with the option `trim_trailing_white_space_on_save` set to true.

### Vim

- By default does not show trailing whitespace. To show it, turn on ['list'](http://vimdoc.sourceforge.net/htmldoc/options.html#%27list%27) option.
- Trimming trailing whitespace automatically or manually is possible. See [this tip](http://vim.wikia.com/wiki/Remove_unwanted_spaces).