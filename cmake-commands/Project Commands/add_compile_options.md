## add_compile_options

Add options to the compilation of source files.

```
add_compile_options(<option> ...)
```

Adds options to the `COMPILE_OPTIONS` directory property. These options are used when compiling targets from the current directory and below.

> Note: These options are not used when linking. See the `add_link_options()` command for that.
