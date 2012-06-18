# Current and Future EditorConfig Properties

This document details current EditorConfig properties and ideas for future properties (both standard and non-standard).

## Current Standard Properties

<table>
	<thead>
		<tr><th>Property</th><th>Possible Values</th><th>Purpose</th></tr>
	</thead>
	<tbody>
		<tr><td>indent_style</td><td>"tab" or "space"</td><td>Indentation Style</td></tr>
		<tr><td>indent_size</td><td>"tab" or an integer</td><td>Indentation Size (in single-spaced characters)</td></tr>
		<tr><td>tab_width</td><td>integer (defaults "indent_size" when it is a number)</td><td>Width of a single tabstop character</td></tr>
		<tr><td>end_of_line</td><td>"LF", "CR", or "CRLF"</td><td>Line ending file format (Unix, Mac, DOS)</td></tr>
	</tbody>
</table>

## Ideas for Future Universal Properties

<table>
	<thead>
		<tr><th>Property</th><th>Possible Values</th><th>Purpose</th></tr>
	</thead>
	<tbody>
		<tr><td>byte_order_mark</td><td>"true" or "false"</td><td>Denotes whether a byte order mark should be added to file</td></tr>
		<tr><td>charset</td><td>"latin1", "UTF-8", "UTF-16BE", "UTF-16LE"</td><td>File character encoding</td></tr>
		<tr><td>allow_trailing_space</td><td>"true" or "false"</td><td>Denotes whether whitespace is allowed at the end of lines</td></tr>
		<tr><td>indent_blank_lines</td><td>"true" or "false"</td><td>Denotes whether blank lines should contain indented whitespace</td></tr>
		<tr><td>newline_at_end_of_file</td><td>"true" or "false"</td><td>Denotes whether file should end with a newline</td></tr>
		<tr><td>spaces_around_operators</td><td>"true" or "false"</td><td>Denotes whether spaces should be present around arithmetic and boolean operators</td></tr>
	</tbody>
</table>

## Ideas for Future Domain Specific Properties

<table>
	<thead>
		<tr><th>Property</th><th>Possible Values</th><th>Purpose</th></tr>
	</thead>
	<tbody>
		<tr><td>quote_type</td><td>"single" or "double"</td><td>Denotes preferred quoting style for string literals (for languages that support multiple quote styles)</td></tr>
		<tr><td>c_include_path</td><td>Directory paths separated by colon (<code>:</code>)</td><td>Denotes the include paths of header files for some C family languages, such as C, C++, D, Objective-C, etc. Could be used by syntax checkers and compilers inside editors.</td></tr>
		<tr><td>java_class_path</td><td>Denotes the CLASSPATH used by the Java source files. Could be used by some Java syntax checkers and compilers inside editors.</td></tr>
		<tr><td>curly_bracket_next_line</td><td>"true" or "false"</td><td>Denotes whether the left part of the curly bracket should be on the next line or not for some C family languages, such as C, C++, Java, Javascript, etc.</td><tr>
	</tbody>
</table>

_* Some of the options above are inspired by [codepainter](https://github.com/fawek/codepainter)._
