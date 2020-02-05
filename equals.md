## Equality

- `=`, use for assignment
- `==`, try to avoid it, it is used in conditionals where java tries to
        automatically convert data types;
- `===`, equality;
- `!==`, non-equality;


The best practice here is to always use the identically equal operator
which is `===` or identically non-equal operator `!==`, since those
will give us false if we are comparing different data types.

Be aware that `==` usage can lead to logic errors or errors difficult
to debug, since for `==` `1 == "1"` returns `true`.

