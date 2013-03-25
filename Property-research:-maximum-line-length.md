Issue [#89](https://github.com/editorconfig/editorconfig/issues/89).

## Option for setting a maximum length for each line

A `max_line_length` option (or similarly named option) will force hard line wrapping after the amount of characters specified.

## Behavior

When the typing, the editor automatically wraps the current word to a new line if it reaches the given limit.

## Naming ideas

- text_width
- line_width
- wrap_width
- max_line_length

## Concerns

- How should line length be set when tabs are used?
- Should line be wrapped immediately once length is hit or once line is left/Enter is pressed?
- Should this be disable-able by the user in case they want to control this manually?


## Support in Editors

### Sublime Text 2

The setting is `wrap_width`

### Vim

The setting is `textwidth`.

```
Maximum width of text that is being inserted.  A longer line will be
broken after white space to get this width.  A zero value disables
this.  'textwidth' is set to 0 when the 'paste' option is set.  When
'textwidth' is zero, 'wrapmargin' may be used.  See also
'formatoptions' and ins-textwidth.
When 'formatexpr' is set it will be used to break the line.
NOTE: This option is set to 0 when 'compatible' is set.
```

### Emacs

TODO

### Geany

TODO

### Notepad++

TODO

### Gedit

TODO

### jEdit

TODO

### Code::Blocks

TODO