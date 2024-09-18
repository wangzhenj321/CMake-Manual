## target_compile_definitions

Add compile definitions to a target.

```
target_compile_definitions(<target>
  <INTERFACE|PUBLIC|PRIVATE> [items1...]
  [<INTERFACE|PUBLIC|PRIVATE> [items2...] ...])
```

Specifies compile definitions to use when compiling a given `<target>`. The named `<target>` must have been created by a command such as `add_executable()` or `add_library()` and must not be an ALIAS target.

The `INTERFACE`, `PUBLIC` and `PRIVATE` keywords are required to specify the scope of the following arguments.

- `PRIVATE` and `PUBLIC` items will populate the `COMPILE_DEFINITIONS` property of `<target>`.
- `PUBLIC` and `INTERFACE` items will populate the `INTERFACE_COMPILE_DEFINITIONS` property of `<target>`.

The following arguments specify compile definitions. Repeated calls for the same `<target>` append items in the order called.

Arguments to `target_compile_definitions` may use generator expressions with the syntax `$<...>`. 

Any leading `-D` on an item will be removed. Empty items are ignored. For example, the following are all equivalent:

```
target_compile_definitions(foo PUBLIC FOO)
target_compile_definitions(foo PUBLIC -DFOO)  # -D removed
target_compile_definitions(foo PUBLIC "" FOO) # "" ignored
target_compile_definitions(foo PUBLIC -D FOO) # -D becomes "", then ignored
```

Definitions may optionally have values:

```
target_compile_definitions(foo PUBLIC FOO=1)
```

Note that many compilers treat `-DFOO` as equivalent to `-DFOO=1`, but other tools may not recognize this in all circumstances (e.g. IntelliSense).
