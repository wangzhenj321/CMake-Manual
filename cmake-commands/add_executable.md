## add_executable

Add an executable to the project using the specified source files.

### Normal Executables

```
add_executable(<name> [WIN32] [MACOSX_BUNDLE]
               [EXCLUDE_FROM_ALL]
               [source1] [source2 ...])
```

Adds an executable target called `<name>` to be built from the source files listed in the command invocation. The `<name>` corresponds to the logical target name and must be globally unique within a project. The actual file name of the executable built is constructed based on conventions of the native platform (such as `<name>.exe` or just `<name>`).

By default the executable file will be created in the build tree directory corresponding to the source tree directory in which the command was invoked.

### Imported Executables

### Alias Executables
