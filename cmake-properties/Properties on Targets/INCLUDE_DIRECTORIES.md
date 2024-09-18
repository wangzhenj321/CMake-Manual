## INCLUDE_DIRECTORIES

List of preprocessor include file search directories.

This property specifies the list of directories given so far to the `target_include_directories()` command. In addition to accepting values from that command, values may be set directly on any target using the `set_property()` command. A target gets its initial value for this property from the value of the `INCLUDE_DIRECTORIES` **directory property**. Both directory and target property values are adjusted by calls to the `include_directories()` command.

The value of this property is used by the generators to set the include paths for the compiler.

Relative paths should not be added to this property directly. Use one of the commands above instead to handle relative paths.

Contents of `INCLUDE_DIRECTORIES` may use cmake-generator-expressions(7) with the syntax `$<...>`. 
