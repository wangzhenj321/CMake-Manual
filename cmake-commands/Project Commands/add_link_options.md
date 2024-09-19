## add_link_options

Add options to the link step for executable, shared library or module library targets in the current directory and below that are added after this command is invoked.

```
add_link_options(<option> ...)
```

This command can be used to add any link options, but alternative commands exist to add libraries (`target_link_libraries()` or `link_libraries()`).

> Note: This command cannot be used to add options for static library targets, since they do not use a linker. To add archiver or MSVC librarian flags, see the `STATIC_LIBRARY_OPTIONS` target property.

Arguments to `add_link_options` may use generator expressions with the syntax `$<...>`.
