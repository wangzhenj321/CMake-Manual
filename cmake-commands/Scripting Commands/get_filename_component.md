## get_filename_component

Get a specific component of a full filename.

```
get_filename_component(<var> <FileName> <mode> [CACHE])
```

Sets `<var>` to a component of `<FileName>`, where `<mode>` is one of:

```
DIRECTORY = Directory without file name
NAME      = File name without directory
EXT       = File name longest extension (.b.c from d/a.b.c)
NAME_WE   = File name with neither the directory nor the longest extension
LAST_EXT  = File name last extension (.c from d/a.b.c)
NAME_WLE  = File name with neither the directory nor the last extension
PATH      = Legacy alias for DIRECTORY (use for CMake <= 2.8.11)
```

```
get_filename_component(<var> <FileName> <mode> [BASE_DIR <dir>] [CACHE])
```

Sets `<var>` to the absolute path of `<FileName>`, where `<mode>` is one of:

```
ABSOLUTE  = Full path to file
REALPATH  = Full path to existing file with symlinks resolved
```

If the provided `<FileName>` is a relative path, it is evaluated relative to the given base directory `<dir>`. If no base directory is provided, the default base directory will be `CMAKE_CURRENT_SOURCE_DIR`.
