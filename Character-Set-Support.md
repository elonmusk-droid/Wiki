# Supported Character Sets

We should decide which character sets to support for each/all plugins.  Other character sets could be specified outside of this set and they would be ignored if not understood by the editor.  This is simply a list of character sets that all plugins should attempt to support at a minimum.

- [UTF-8](https://en.wikipedia.org/wiki/UTF-8)
- [Latin](https://en.wikipedia.org/wiki/Latin-1)

# Setting Character Set in text editors

## Vim

Vim character encodings can be set with the `filencoding` command ([see documentation](http://vimdoc.sourceforge.net/htmldoc/options.html#'fileencoding')).

#### Setting UTF-8

    set fileencoding=utf-8

#### Setting Latin1

    set fileencoding=latin1


## emacs

As noted [here](http://www.emacswiki.org/emacs/EndOfLineTips), emacs character encodings and end of line formats are both set using the `set-buffer-file-coding-system` command.

#### Setting UTF-8

    (set-buffer-file-coding-system 'utf-8-unix)
    (set-buffer-file-coding-system 'utf-8-dos)
    (set-buffer-file-coding-system 'utf-8-mac)

#### Setting Latin1

    (set-buffer-file-coding-system 'iso-latin-1-unix)
    (set-buffer-file-coding-system 'iso-latin-1-dos)
    (set-buffer-file-coding-system 'iso-latin-1-mac)