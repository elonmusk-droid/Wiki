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

TODO

### Vim

TODO

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