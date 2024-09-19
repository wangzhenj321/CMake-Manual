## add_compile_definitions

Add preprocessor definitions to the compilation of source files.

```
add_compile_definitions(<definition> ...)
```

Adds preprocessor definitions to the compiler command line.

The preprocessor definitions are added to the `COMPILE_DEFINITIONS` directory property for the current CMakeLists file. They are also added to the `COMPILE_DEFINITIONS` target property for each target in the current CMakeLists file.

Definitions are specified using the syntax `VAR` or `VAR=value`. Function-style definitions are not supported. CMake will automatically escape the value correctly for the native build system (note that CMake language syntax may require escapes to specify some values).

Arguments to `add_compile_definitions` may use generator expressions with the syntax `$<...>`.

> Note: The command `target_compile_definitions()` adds target-specific definitions.
