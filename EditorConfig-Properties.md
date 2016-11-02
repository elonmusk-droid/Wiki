# Current and Future EditorConfig Properties

This document details current EditorConfig properties and ideas for future properties (both universal and domain-specific).

# Universal vs. Domain-Specific

**Universal properties** are those which can have a meaning for nearly every file format.

**Domain-specific properties** are those which may not be meaningful for some file formats.

# Current Universal Properties

## Widely Supported by Editors

### `indent_style`

Indentation Style

_The values are case insensitive. They will be lowercased by the core library._

**Possible Values**

- `tab`
- `space`

**Supported By**

- all plugins

### `indent_size`

Indentation Size (in single-spaced characters)

_The values are case insensitive. They will be lowercased by the core library._

**Possible Values**

- an integer
- `tab`

**Supported By**

- all plugins

### `tab_width`

Width of a single tabstop character

**Possible Values**

- a positive integer (defaults `indent_size` when `indent_size` is a number)

**Supported By**

- all plugins

### `end_of_line`

Line ending file format (Unix, DOS, Mac)

_The values are case insensitive. They will be lowercased by the core library._

**Possible Values**

- `lf`
- `crlf`
- `cr`

**Supported By**

- all plugins

### `charset`

File character encoding

_The values are case insensitive. They will be lowercased by the core library._

**Possible Values**

- `latin1`
- `utf-8`
- `utf-16be`
- `utf-16le`

### `trim_trailing_whitespace`

Denotes whether whitespace is allowed at the end of lines

_The values are case insensitive. They will be lowercased by the core library._

**Possible Values**

- `true`
- `false`

### `insert_final_newline`

Denotes whether file should end with a newline

_The values are case insensitive. They will be lowercased by the core library._

**Possible Values**

- `true`
- `false`

## Supported By A Limited Number of Editors

### `max_line_length`

Forces hard line wrapping after the amount of characters specified. `off` to
turn off this feature (use the editor settings).

**Possible Values**

- positive integers
- `off`

**Supported By**

- Emacs
- Vim
- Atom

# Ideas for Domain-Specific Properties

The following properties are not intended to be implemented by EditorConfig.  
This is simply a brainstorm of domain-specific properties that could be supported by 
some tools that rely on EditorConfig files.

<table>
    <caption>Ideas for Domain-Specific Properties</caption>
    
    <thead>
        <tr>
            <th>Property</th>
            <th>Possible Values</th>
            <th>Purpose</th>
            <th>Domain</th>
        </tr>
    </thead>
    
    <tbody>
        <tr>
            <td><code>quote_type</code></td>
            <td><code>single</code>, <code>double</code>, <code>auto</code></td>
            <td>Denotes preferred quoting style for string literals (for languages that support multiple quote styles)</td>
            <td>with multiple equivalent string literal quote types</td>
        
        </tr><tr>
            
            <td><code>c_include_path</code></td>
            <td>Directory paths separated by colon (<code>:</code>)</td>
            <td>Denotes the include paths of header files for some languages. 
                Could be used by syntax checkers and compilers inside editors.</td>
            <td>C-family languages (such as C, C++, D, Objective-C, etc.)</td>
        
        </tr><tr>
            
            <td><code>java_class_path</code></td>
            <td>Paths separated by colon (<code>:</code>)</td>
            <td>Denotes the <code>CLASSPATH</code> used by the Java source files. 
                Could be used by some Java syntax checkers and compilers inside editors.</td>
            <td>Java</td>
        
        </tr><tr>
            
            <td><code>curly_bracket_next_line</code></td>
            <td><code>true</code>, <code>false</code></td>
            <td>Denotes whether the left part of the curly bracket should be on the next line or not</td>
            <td>C-family languages (such as C, C++, Java, Javascript, etc.)</td>
        
        </tr><tr>
            
            <td><code>spaces_around_operators</code></td>
            <td><code>true</code>, <code>false</code>, <code>hybrid</code></td>
            <td>Denotes whether spaces should be present around arithmetic and boolean operators</td>
            <td>with infix operators and optional spaces</td>
        
        </tr><tr>
            
            <td><code>spaces_around_brackets</code></td>
            <td><code>none</code>, <code>inside</code>, <code>outside</code>, <code>both</code></td>
            <td>Denotes how spaces should be around brackets and parentheses: 
                no space, only inside the brackets, only outside the brackets, or at the both side of brackets
            </td>
            <td></td>
        
        </tr><tr>
            
            <td><code>indent_brace_style</code></td>
            <td><code>K&amp;R</code>, <code>Allman</code>, <code>GNU</code>, <code>Horstmann</code>, etc.</td>
            <td>Denotes the <a href="https://en.wikipedia.org/wiki/Indent_style">style for using curly braces</a> in code blocks</td>
            <td>C-family languages (such as C, C++, Java, Javascript, etc.) with code blocks using curly braces</td>
        <tr>
            
            <td><code>Number of imports required for '*'</code></td>
            <td>int</td>
            <td>Denotes the number of imports required before multiple imports are automatically collapsed to a wildcard (or a wildcard is automatically expanded to explicit imports)</td>
            <td>Java etc. (Eclipse and IDEA already have the core functionality)</td>
        </tr>
        <tr>
            <td><code>continuation_indent_size</code></td>
            <td>unsigned integer</td>
            <td>Denotes the continuation indent size.  Useful to distinguish code blocks versus continuation lines</td>
            <td>Python, JetBrains (IntelliJ IDEA)</td>
        </tr>
        <tr>
            <td><code>block_comment, line_comment, block_comment_start, block_comment_end</code></td>
            <td>char</td>
            <td>Denotes the block_comment or line_comment character to mark a block or each line as comment. Some languages require <code>#</code> predended on each line, others <code>//</code> or <code>;</code>. Some have specific block start markers and end markers such as <code>/*</code> and <code>*/</code> and <code>&lt;!--</code> and <code>--!&gt;</code></td>
            <td>Python, configfiles, yml, ini, JetBrains (Pycharm, IntelliJ IDEA)</td>
        </tr>
    </tbody>

</table>

_* Some of the options above are inspired by [codepainter](https://github.com/jedhunsaker/codepainter)._
