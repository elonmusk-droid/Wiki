## How to propose changes to the format, including new properties and values?

To propose changes, please open an issue at the [issue tracker](https://github.com/editorconfig/editorconfig/issues). Then, after short discussion, we will start reviewing the format change following the rules described [here](https://github.com/editorconfig/editorconfig/wiki/Board-Member) to be voted by current board members.

## My files are not automatically reformatted, the EditorConfig plugin is not working!

Existing files are not reformatted by the plugin (only newly input lines are formatted in the format given in the `.editorconfig` files) but if you would like to use a separate tool to do this then see the next question.

## Are there any tools to check or/and reformat existing files against EditorConfig rules?

Yes! You might like to try:

- [editorconfig-tools](https://github.com/treyhunner/editorconfig-tools)
- [eclint](https://github.com/jedmao/eclint)
- [editorconfig-cf](https://github.com/xuhdev/editorconfig-cf)
- [editorconfig-maven-plugin](https://github.com/ec4j/editorconfig-maven-plugin)
- [editorconfig-gradle-plugin](https://github.com/ec4j/editorconfig-gradle-plugin)
- [editorconfig-checker](https://github.com/editorconfig-checker/editorconfig-checker)

You could use one of these tools to tidy up existing code in a repository, and then set it to [run as a continuous integration test](https://github.com/editorconfig/editorconfig/issues/362) to ensure code stays tidy in the future, but please note that none of these tools work perfectly at the moment.

## When using the Vim plugin, I got `E887: Sorry, this command is disabled, the Python's site module could not be loaded.`

It is likely to happen on macOS with Vim and Python installed using Homebrew. It usually happens after a Python upgrade, at which time the old Vim installation does not recognize the new Python installation. To fix it, run `brew reinstall vim` or `brew reinstall macvim`. If it didn't help, try to recompile Vim locally running `brew reinstall vim --with-custom-python` or `brew reinstall macvim --with-custom-python`. For more info, check `brew info vim` / `brew info macvim`.

## The executable of EditorConfig core does not accept relative paths. How can I fix that?

Since EditorConfig core executables are usually not supposed to be called by humans from command line, we did not support relative paths for simplicity across all implementations of EditorConfig cores. However, if you really need to call it from the command line (e.g., for debugging), you can use the following way to call it on a POSIX system, if the `realpath` utility is available on your system:

    editorconfig $(realpath my-file.ext)

or use the following command, if `realpath` is unavailable:

    editorconfig $(pwd)/my-file.ext