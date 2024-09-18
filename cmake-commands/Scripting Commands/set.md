## set

Set a normal, cache, or environment variable to a given value.

Signatures of this command that specify a `<value>...` placeholder expect zero or more arguments. Multiple arguments will be joined as a semicolon-separated list to form the actual variable value to be set.

### Set Normal Variable

```
set(<variable> <value>... [PARENT_SCOPE])
```

Set or unset `<variable>` in the current function or directory scope:

- If at least one `<value>...` is given, set the variable to that value.
- If no value is given, unset the variable. This is equivalent to `unset(<variable>)`.

### Set Cache Entry

```
set(<variable> <value>... CACHE <type> <docstring> [FORCE])
```

Sets the given cache `<variable>` (cache entry). Since cache entries are meant to provide user-settable values this does not overwrite existing cache entries by default. Use the `FORCE` option to overwrite existing entries.

The <type> must be specified as one of:

- `BOOL`

    Boolean `ON/OFF` value.

- `FILEPATH`

    Path to a file on disk.

- `PATH`

    Path to a directory on disk.

- `STRING`

    A line of text. 

- `INTERNAL`

    A line of text. They may be used to store variables persistently across runs. Use of this type implies `FORCE`.

The `<docstring>` must be specified as a line of text providing a quick summary of the option for presentation to cmake-gui(1) users.

If the cache entry does not exist prior to the call or the `FORCE` option is given then the cache entry will be set to the given value.

### Set Environment Variable

```
set(ENV{<variable>} [<value>])
```

Sets an Environment Variable to the given value. Subsequent calls of `$ENV{<variable>}` will return this new value.

This command affects only the current CMake process, not the process from which CMake was called, nor the system environment at large, nor the environment of subsequent build or test processes.

If no argument is given after `ENV{<variable>}` or if `<value>` is an empty string, then this command will clear any existing value of the environment variable.

### References

1. https://blog.csdn.net/Calvin_zhou/article/details/104060927
