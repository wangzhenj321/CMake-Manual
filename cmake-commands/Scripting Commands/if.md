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
