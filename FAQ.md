## My files are not automatically reformatted, the EditorConfig plugin is not working!

Existing files are not reformatted. Only newly input lines are formatted in the format given in the `.editorconfig` files. If you are looking for a tool to check or/and reformat your existing files, check [editorconfig-tools](https://github.com/treyhunner/editorconfig-tools), [eclint](https://github.com/jedmao/eclint) and [editorconfig-cf](https://github.com/xuhdev/editorconfig-cf) (None of them works perfectly though).

## When using the Vim plugin, I got `E887: Sorry, this command is disabled, the Python's site module could not be loaded.`

It is likely to happen on OS X with Vim and Python installed using Homebrew. It usually happens after a Python upgrade, which the old Vim installation does not recognize the new Python installation. To fix it, run `brew reinstall vim` or `brew reinstall macvim`.

## The executable of EditorConfig core does not accept relative paths. How can I fix that?

Since EditorConfig core executables are usually not supposed to be called by humans from command line, we did not support relative paths for simplicity across all implementations of EditorConfig cores. However, if you really need to call it from the command line (e.g., for debugging), you can use the following way to call it on a POSIX system, if the `realpath` utility is available on your system:

    editorconfig $(realpath my-file.ext)

or use the following command, if `realpath` is unavailable:

    editorconfig $(pwd)/my-file.ext