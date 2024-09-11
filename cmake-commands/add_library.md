## add_library

Add a library to the project using the specified source files.

### Normal Libraries

```
add_library(<name> [STATIC | SHARED | MODULE]
            [EXCLUDE_FROM_ALL]
            [<source>...])
```

Adds a library target called `<name>` to be built from the source files listed in the command invocation. The `<name>` corresponds to the logical target name and must be globally unique within a project. The actual file name of the library built is constructed based on conventions of the native platform (such as `lib<name>.a` or `<name>.lib`).

`STATIC`, `SHARED`, or `MODULE` may be given to specify the type of library to be created.

- `STATIC` libraries are archives of object files for use when linking other targets.
- `SHARED` libraries are linked dynamically and loaded at runtime.
- `MODULE` libraries are plugins that are not linked into other targets but may be loaded dynamically at runtime using dlopen-like functionality.

If no type is given explicitly the type is `STATIC` or `SHARED` based on whether the current value of the variable `BUILD_SHARED_LIBS` is ON.

### Object Libraries

### Interface Libraries

### Imported Libraries

### Alias Libraries
