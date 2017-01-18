# Guidelines for writing a plugin

You've decided to write a new plugin for your favorite editor or contribute to an already-existing plugin, but it's not always clear when or how to apply an EditorConfig setting. Here are some guidelines for each property and how to handle them in the most effective and unobtrusive way.

## `indent_style`

1. When opening/switching to a file, apply built-in editor setting.
1. If no built-in editor setting, do nothing. Do not attempt to fix indent style with manual operations.

## `indent_size`

1. When opening/switching to a file, apply built-in editor setting.
1. If no built-in editor setting, do nothing. Do not attempt to fix indent size with manual operations.

## `tab_width`

1. When opening/switching to a file, apply built-in editor setting.
1. If no built-in editor setting, do nothing. Manual operations do not apply to this property.

## `end_of_line`

1. When opening/switching to a file, apply built-in editor setting. In some editors, this will mark the file as dirty.
1. If no built-in editor setting, apply built-in editor operation on file save.
1. If no built-in editor operation, apply manual operation on file save or do nothing.

## `charset`
1. When opening/switching to a file, apply built-in editor setting.
1. If no built-in editor setting, apply manual operation on file save or do nothing.

## `trim_trailing_whitespace`
1. Do not attempt to fix trailing whitespace when opening/switching to a file.
1. Apply built-in editor setting on file save.
1. If no built-in editor setting, apply manual operation on file save or do nothing.

## `insert_final_newline`

1. Do not attempt to insert a final new line when opening/switching to a file.
1. On file save, apply built-in editor setting.
1. If no built-in editor setting, apply manual operation on file save or do nothing.