## This is not about how EditorConfig works today

If you are looking for information about how EditorConfig works or its present behaviour, please ignore this page!  Thank you!

## Overview

This page is for consideration of questions being discussed in issues:

 - [#190](https://github.com/editorconfig/editorconfig/issues/190) Apply file type (e.g., for syntax highlighting) based on EditorConfig property
 - [#239](https://github.com/editorconfig/editorconfig/issues/239) Shell script language detection
 - [#404](https://github.com/editorconfig/editorconfig/issues/404) Introduction of `[[language]]` support
 - [#405](https://github.com/editorconfig/editorconfig/issues/405) What file-type values will be recognized?
 - [#406](https://github.com/editorconfig/editorconfig/issues/406) How should file types be mapped to editor-specific values?
 - [#407](https://github.com/editorconfig/editorconfig/issues/407) How should a global file type map (if any) be stored/used?
 - [editorconfig-emacs #75](https://github.com/editorconfig/editorconfig-emacs/issues/75)

Also related:
 - [dlenski/wtf#15](https://github.com/dlenski/wtf/issues/15)
 - [mvdan/sh#393](https://github.com/mvdan/sh/issues/393)

## Current dataflow

 - The editor loads a file
 - The plugin gets the path of the file and invokes the core
 - The core reads `.editorconfig` file(s) and returns settings to the plugin
 - The plugin applies the settings to the editor window holding the file

## Limitations of the current dataflow that have been identified in issues

 - When mixing extensionless files with different settings in a directory, you have to list each file individually to have the appropriate settings applied (#239: [report](https://github.com/editorconfig/editorconfig/issues/239#issue-117118155); [example of listing all files](https://github.com/editorconfig/editorconfig/issues/239#issuecomment-157150735)).
 - EditorConfig currently applies settings only based on file path, not on file type (#404)
 - EditorConfig does not currently have a property to set syntax-highlighting rules in the editor (e.g., `sh` vs. `bash`) (#190)
 - The EditorConfig file format is not currently designed for interoperability with other tools (dlenski/wtf#14, mvdan/sh#393).

## Summary

These issues all seem to be asking that EditorConfig be aware of the filetype when choosing settings for a file.

## Some challenges

 - Determining the type of a file is hard (https://github.com/editorconfig/editorconfig/issues/404#issuecomment-532617490).
   - E.g., `sh` vs. `bash`.  What if a `#!/bin/sh` file uses bash-specific `if [[ ]]`?
 - Different editors use different names for programming languages/filetypes (e.g., vscode's list, Ace's list, and Vim's filetype list)
 - EditorConfig installation and use still needs to be simple
 - Our current core/plugin split keeps the core independent of specific plugins (which is good) but makes it harder for the core to access editor-specific information (but see an example of a hack in https://github.com/editorconfig/editorconfig-emacs/issues/75#issuecomment-350182935).