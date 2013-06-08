# Current and Future EditorConfig Properties

This document details current EditorConfig properties and ideas for future properties (both universal and domain-spcecific).

# Universal vs. Domain-Specific

**Universal properties** are those which can have a meaning for nearly every file format.

**Domain-specific properties** are those which may not be meaningful for some file formats.

# Current Universal Properties

## indent_style

Indentation Style

_The values are case insensitive. They will be lowercased by the core library._

### Possible Values

- "tab"
- "space"

## indent_size

Indentation Size (in single-spaced characters)

_The values are case insensitive. They will be lowercased by the core library._

### Possible Values

- an integer
- "tab"

## tab_width

Width of a single tabstop character

### possible values

- a positive integer (defaults "indent_size" when "indent_size" is a number)

## end_of_line

Line ending file format (Unix, DOS, Mac)

_The values are case insensitive. They will be lowercased by the core library._

### possible values

- "lf"
- "cr"
- "crlf"

## charset

File character encoding

_The values are case insensitive. They will be lowercased by the core library._

### possible values

- "latin1"
- "utf-8"
- "utf-16be"
- "utf-16le"

## trim_trailing_whitespace

Denotes whether whitespace is allowed at the end of lines

_The values are case insensitive. They will be lowercased by the core library._

### possible values

- "true"
- "false"

## insert_final_newline

Denotes whether file should end with a newline

_The values are case insensitive. They will be lowercased by the core library._

### possible values
- "true"
- "false"

## Ideas for Domain-Specific Properties

The following properties are not intended to be implemented by EditorConfig.  This is simply a brainstorm of domain-specific properties that could be supported by some tools that rely on EditorConfig files.

<table>
	<thead>
		<tr><th>Property</th><th>Possible Values</th><th>Purpose</th><th>Domain</th></tr>
	</thead>
	<tbody>
		<tr><td>quote_type</td><td>"single" or "double"</td><td>Denotes preferred quoting style for string literals (for languages that support multiple quote styles)</td><td>with multiple equivalent string literal quote types</td></tr>
		<tr><td>c_include_path</td><td>Directory paths separated by colon (<code>:</code>)</td><td>Denotes the include paths of header files for some C family languages, such as C, C++, D, Objective-C, etc. Could be used by syntax checkers and compilers inside editors.</td><td></td></tr>
		<tr><td>java_class_path</td><td>Paths separated by colon (<code>:</code>)</td><td>Denotes the CLASSPATH used by the Java source files. Could be used by some Java syntax checkers and compilers inside editors.</td><td>Java</td></tr>
		<tr><td>curly_bracket_next_line</td><td>"true" or "false"</td><td>Denotes whether the left part of the curly bracket should be on the next line or not for some C family languages, such as C, C++, Java, Javascript, etc.</td><td></td><tr>
		<tr><td>spaces_around_operators</td><td>"true" or "false"</td><td>Denotes whether spaces should be present around arithmetic and boolean operators</td><td>with infix operators and optional spaces</td></tr>
		<tr><td>spaces_around_brackets</td><td>"none", "inside", "outside", or "both"</td><td>Denotes how spaces should be around brackets and parentheses: no space, only inside the brackets, only outside the brackets, or at the both side of brackets</td><td></td></tr>
		<tr><td>indent_brace_style</td><td>"K&R", "Allman", "GNU", "Horstmann", etc.</td><td>Denotes the <a href="https://en.wikipedia.org/wiki/Indent_style">style for using curly braces</a> in code blocks</td><td>languages with C-style code blocks using curly braces</td></tr>
	</tbody>
</table>

_* Some of the options above are inspired by [codepainter](https://github.com/fawek/codepainter)._
