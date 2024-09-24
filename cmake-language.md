## Variables

Variables are the basic unit of storage in the CMake Language. Their values are always of string type, though some commands may interpret the strings as values of other types. The `set()` and `unset()` commands explicitly set or unset a variable, but other commands have semantics that modify variables as well. Variable names are case-sensitive and may consist of almost any text, but we recommend sticking to names consisting only of alphanumeric characters plus `_` and `-`.

Variables have dynamic scope. Each variable "set" or "unset" creates a binding in the current scope:

- Block Scope

    The `block()` command may create a new scope for variable bindings.

- Function Scope

    Command Definitions created by the `function()` command create commands that, when invoked, process the recorded commands in a new variable binding scope. A variable "set" or "unset" binds in this scope and is visible for the current function and any nested calls within it, but not after the function returns.

- Directory Scope

    Each of the Directories in a source tree has its own variable bindings. Before processing the CMakeLists.txt file for a directory, CMake copies all variable bindings currently defined in the parent directory, if any, to initialize the new directory scope. CMake Scripts, when processed with `cmake -P`, bind variables in one "directory" scope.

    A variable "set" or "unset" not inside a function call binds to the current directory scope.

- Persistent Cache

    CMake stores a separate set of "cache" variables, or "cache entries", whose values persist across multiple runs within a project build tree. Cache entries have an isolated binding scope modified only by explicit request, such as by the `CACHE` option of the `set()` and `unset()` commands.

When evaluating Variable References, CMake first searches the function call stack, if any, for a binding and then falls back to the binding in the current directory scope, if any. If a "set" binding is found, its value is used. If an "unset" binding is found, or no binding is found, CMake then searches for a cache entry. If a cache entry is found, its value is used. Otherwise, the variable reference evaluates to an empty string. The `$CACHE{VAR}` syntax can be used to do direct cache entry lookups.
