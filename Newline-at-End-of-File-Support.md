# Editor Support for Newline Insertion at End of File

## Option for Inserting Newlines at End of File

An `insert_final_newline` option (or similarly named option) will control whether a newline is automatically inserted at the end of a file on save (when a newline is missing).

Understood values for this option will be:

- `true`: a newline will be inserted at the end of the file automatically
- `false`: no newline will be inserted at the end of the file automatically


## Naming ideas

The options would be `true` and `false` and would have the same behavior as descripbed above for all of the below option names.

Names this option might have:
- insert_final_newline
- require_final_newline
- insert_newline_at_end_of_file

## Support in Editors

### Vim

Default behavior:
- doesn't show the last newline at the end of the file
- automatically adds a newline when saving files

Automatic newline insertion can be disabled by enabling [binary][] file editing and disabling the [endofline][] option.  We may be able to use [this method](http://stackoverflow.com/a/4152785/98187) of disabling newline insertion on write for the Vim plugin.  One notable quirk with this method is that setting `binary` forces LF line endings so this method cannot be used for files with CRLF line endings which would probably be the most common case for this option.  [This vim tip on preserving missing newlines at end of file][tip 1369] may help resolve this issue.

[binary]: http://vimdoc.sourceforge.net/htmldoc/options.html#'binary'
[endofline]: http://vimdoc.sourceforge.net/htmldoc/options.html#'endofline'
[tip 1369]: http://vim.wikia.com/wiki/Preserve_missing_end-of-line_at_end_of_text_files


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


### Sublime Text 2

Default behavior:
- Shows the last newline at the end of the file
- Does not add a newline when saving files by default

This behavior can be changed by setting the `ensure_newline_at_eof_on_save` option to `true`.
