## target_include_directories

Add include directories to a target.

```
target_include_directories(<target> [SYSTEM] [AFTER|BEFORE]
  <INTERFACE|PUBLIC|PRIVATE> [items1...]
  [<INTERFACE|PUBLIC|PRIVATE> [items2...] ...])
```

Specifies include directories to use when compiling a given target. The named `<target>` must have been created by a command such as `add_executable()` or `add_library()` and must not be an ALIAS target.

By using `AFTER` or `BEFORE` explicitly, you can select between appending and prepending, independent of the default.

The `INTERFACE`, `PUBLIC` and `PRIVATE` keywords are required to specify the scope of the following arguments. `PRIVATE` and `PUBLIC` items will populate the `INCLUDE_DIRECTORIES` property of `<target>`. `PUBLIC` and `INTERFACE` items will populate the `INTERFACE_INCLUDE_DIRECTORIES` property of `<target>`. The following arguments specify include directories.

Repeated calls for the same `<target>` append items in the order called.
