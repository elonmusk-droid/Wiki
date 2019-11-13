`.editorconfig` files are INI files with a simple syntax defined in [the spec](https://editorconfig-specification.readthedocs.io/en/latest/).

It is somewhat compatible with the format used by [Python ConfigParser Library](http://docs.python.org/2/library/configparser.html). But there are a few noticeable points:

- `[` and `]` can be used inside the sections (`[...]`);
- Comments should go in individual lines, we are not sure whether appending comments may cause issues.
- There is no official support for fancy stuff like continuation and quoting.