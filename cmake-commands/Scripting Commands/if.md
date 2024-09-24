## if

Conditionally execute a group of commands.

### Synopsis

```
if(<condition>)
  <commands>
elseif(<condition>) # optional block, can be repeated
  <commands>
else()              # optional block
  <commands>
endif()
```

### Condition Syntax

#### Existence Checks

- `if(TARGET <target-name>)`

    True if the given name is an existing logical target name created by a call to the `add_executable()`, `add_library()`, or `add_custom_target()` command that has already been invoked (in any directory).

- `if(DEFINED <name>|CACHE{<name>}|ENV{<name>})`

    True if a variable, cache variable or environment variable with given `<name>` is defined. The value of the variable does not matter.

#### File Operations

- `if(EXISTS <path-to-file-or-directory>)`

    True if the named file or directory exists and is readable. Behavior is well-defined only for explicit full paths (a leading `~/` is not expanded as a home directory and is considered a relative path). Resolves symbolic links, i.e. if the named file or directory is a symbolic link, returns true if the target of the symbolic link exists.

    False if the given path is an empty string.

#### Version Comparisons

- `if(<variable|string> VERSION_GREATER <variable|string>)`

    Component-wise integer version number comparison (version format is `major[.minor[.patch[.tweak]]]`, omitted components are treated as zero). Any non-integer version component or non-integer trailing part of a version component effectively truncates the string at that point.
