# Supported Character Sets

We should decide which character sets to support for each/all plugins.  Other character sets could be specified outside of this set and they would be ignored if not understood by the editor.  This is simply a list of character sets that all plugins should attempt to support at a minimum.

- [UTF-8](https://en.wikipedia.org/wiki/UTF-8), BOM deprecated.
- [UTF-16](https://en.wikipedia.org/wiki/UTF-16), LE/BE, BOM unspecified.
- [Latin-1](https://en.wikipedia.org/wiki/Latin-1)

If an implementation wishes to define a new character set, it is recommended that it consults outside authorities such as the [WHATWG Encoding Standard](https://encoding.spec.whatwg.org/) and the [IANA Character Set registry](iana.org/assignments/character-sets/character-sets.xhtml). Using a special prefix such as `x-` is neither required nor recommended, as unsupported values are simply ignored.

# Setting character sets in text editors

## Vim

Vim character encodings can be set with the `filencoding` command ([see documentation](http://vimdoc.sourceforge.net/htmldoc/options.html#'fileencoding')).

#### Setting UTF-8

```viml
set fileencoding=utf-8
```

#### Setting Latin1

```viml
set fileencoding=latin1
```

## Emacs

As noted [here](http://www.emacswiki.org/emacs/EndOfLineTips), Emacs character encodings and end-of-line formats are both set using the `set-buffer-file-coding-system` command.

#### Setting UTF-8

```elisp
(set-buffer-file-coding-system 'utf-8-unix)
(set-buffer-file-coding-system 'utf-8-dos)
(set-buffer-file-coding-system 'utf-8-mac)
```

#### Setting Latin1

```elisp
(set-buffer-file-coding-system 'iso-latin-1-unix)
(set-buffer-file-coding-system 'iso-latin-1-dos)
(set-buffer-file-coding-system 'iso-latin-1-mac)
```