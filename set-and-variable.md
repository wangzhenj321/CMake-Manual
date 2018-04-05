## [Variables](https://cmake.org/cmake/help/v3.10/manual/cmake-language.7.html#variables)

Variables are the basic unit of storage in the CMake Language. Their values are always of string type, though some commands may interpret the strings as values of other types. The `set()` and `unset()` commands explicitly set or unset a variable, but other commands have semantics that modify variables as well. Variable names are case-sensitive and may consist of almost any text, but we recommend sticking to names consisting only of alphanumeric characters plus `_` and `-`.

Variables have dynamic scope. Each variable “set” or “unset” creates a binding in the current scope:

- Function Scope
- Directory Scope
- Persistent Cache
  
When evaluating [Variable References](https://cmake.org/cmake/help/v3.10/manual/cmake-language.7.html#variable-references), CMake first searches the function call stack, if any, for a binding and then falls back to the binding in the current directory scope, if any. If a “set” binding is found, its value is used. If an “unset” binding is found, or no binding is found, CMake then searches for a cache entry. If a cache entry is found, its value is used. Otherwise, the variable reference evaluates to an empty string.

The [cmake-variables(7)](https://cmake.org/cmake/help/v3.10/manual/cmake-variables.7.html#manual:cmake-variables(7)) manual documents many variables that are provided by CMake or have meaning to CMake when set by project code.

#### Variable References

- A variable reference has the form ${variable_name}.
- An environment variable reference has the form $ENV{VAR}.

#### cmake-variables(7)

1. CMAKE_LIBRARY_PATH
2. CMAKE_FIND_ROOT_PATH
3. ...
