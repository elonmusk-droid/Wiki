Basically the `.editorconfig` files are compatible with the format used by [Python ConfigParser Library](http://docs.python.org/2/library/configparser.html). But there are a few noticeable points:

- `[` and `]` can be used inside the sections (`[...]`);
- Comments should go in individual lines, we are not sure whether appending comments may cause issues.