## INI format

### Required modifications to this format

* Allow any characters to appear in section names (not just alphanumeric and certain symbols).  For example:

        [*[1964].txt]
        indent_style = space
        indent_size = 2

### Possibly modifications to this format

* Allow property declarations outside of section names (at top of file only).  For example:

        root = true
        [*.py]
        indent_style = space
        indent_size = 4

### Benefits of this format

* Very readable
* Familiar and easy to pick up

### Limitations

* File structure must be list of sections (each with name and hash of properties)
* Only string datatypes natively supported for property values


## YAML format

### Benefits of this format

* Easily readable
* Spaces allowed in key and value names
* Many datatypes supported natively (boolean, numeric, strings, lists, hashes)

### Limitations

* May not be as familiar as INI or XML
* Top level structure uses an unorded hash unless `- ` is prepended to section names
* Section names using symbols (like `*`) must be surrounded by quotes

### Example file

```yaml
- root: true

- "*":
  - end of line: LF

- "*.py":
  - indent style: space
  - indent size: 4

- "*.html":
  - indent style: space
  - indent size: 2
```
