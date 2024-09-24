## target_sources

Add sources to a target.

```
target_sources(<target>
  <INTERFACE|PUBLIC|PRIVATE> [items1...]
  [<INTERFACE|PUBLIC|PRIVATE> [items2...] ...])
```

Specifies sources to use when building a target and/or its dependents. The named `<target>` must have been created by a command such as `add_executable()` or `add_library()` or `add_custom_target()` and must not be an ALIAS target. The `<items>` may use generator expressions.
