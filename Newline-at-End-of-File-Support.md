# Editor Support for Newline Insertion at End of File

## Option for Inserting Newlines at End of File

An `insert_final_newline` option (or similarly named option) will control whether a newline is automatically inserted at the end of a file on save (when a newline is missing).

Understood values for this option will be:

- `true`: a newline will be inserted at the end of the file automatically
- `false`: no newline will be inserted at the end of the file automatically

## Support in Editors

### Vim

Default behavior:
- doesn't show the last newline at the end of the file
- automatically adds a newline when saving files

Automatic newline insertion can be disabled by enabling [binary][] file editing and disabling the [endofline][] option.  We may be able to use [this method](http://stackoverflow.com/a/4152785/98187) of disabling newline insertion on write for the Vim plugin.

[binary]: http://vimdoc.sourceforge.net/htmldoc/options.html#'binary'
[endofline]: http://vimdoc.sourceforge.net/htmldoc/options.html#'endofline'


### Emacs

Default behavior:
- shows the last newline at the end of the file
- automatically adds a newline when saving files

Automatic newline insertion can be disabled by setting the [require-final-newline][] option to `nil`.

[require-final-newline]: http://www.gnu.org/software/emacs/manual/html_node/emacs/Customize-Save.html


### Gedit

Default behavior:
- doesn't show the last newline at the end of the file
- automatically adds a newline when saving files

This [behavior cannot be changed][gedit newlines] in Gedit currently.  Gedit will not be able to support this option.

[gedit newlines]: https://bugs.launchpad.net/ubuntu/+source/gedit/+bug/379367

### Notepad++

Default behavior:
- shows the last newline at the end of the file
- does not automatically add a newline when saving files

### jEdit

Default behavior:
- doesn't show the last newline at the end of the file if the file had
a trailing newline when it was opened
- automatically adds a newline when saving for new files only
(preserves missing newlines in existing files)

### Visual Studio

Default behavior:
- shows the last newline at the end of the file
- does not automatically add a newline when saving

### Geany

Default behavior:
- Shows the last newline at the end of the file
- adds a newline if "Ensure newline at file end" is checked
