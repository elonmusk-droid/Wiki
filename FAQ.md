## My files are not automatically reformatted, the EditorConfig plugin is not working!

Existing files are not reformatted. Only newly input lines are formatted in the format given in the `.editorconfig` files. If you are looking for a tool to check or/and reformat your existing files, check [editorconfig-tools](https://github.com/treyhunner/editorconfig-tools), [eclint](https://github.com/jedmao/eclint) and [editorconfig-cf](https://github.com/xuhdev/editorconfig-cf) (None of them works perfectly though).

## When using the Vim plugin, I got `E887: Sorry, this command is disabled, the Python's site module could not be loaded.`

It is likely to happen on OS X with Vim and Python installed using Homebrew. It usually happens after a Python upgrade, which the old Vim installation does not recognize the new Python installation. To fix it, run `brew reinstall vim` or `brew reinstall macvim`.