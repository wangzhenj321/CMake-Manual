## target_compile_options

Add compile options to a target.

```
target_compile_options(<target> [BEFORE]
  <INTERFACE|PUBLIC|PRIVATE> [items1...]
  [<INTERFACE|PUBLIC|PRIVATE> [items2...] ...])
```

Adds options to the `COMPILE_OPTIONS` or `INTERFACE_COMPILE_OPTIONS` target properties. These options are used when compiling the given `<target>`, which must have been created by a command such as `add_executable()` or `add_library()` and must not be an ALIAS target.

> Note: These options are not used when linking the target. See the `target_link_options()` command for that.
