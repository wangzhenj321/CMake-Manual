## function

Start recording a function for later invocation as a command.

```
function(<name> [<arg1> ...])
  <commands>
endfunction()
```

Defines a function named `<name>` that takes arguments named `<arg1>`, ... The `<commands>` in the function definition are recorded; they are not executed until the function is invoked.

### Invocation

The function invocation is case-insensitive. A function defined as

```
function(foo)
  <commands>
endfunction()
```

can be invoked through any of

```
foo()
Foo()
FOO()
cmake_language(CALL foo)
```

and so on. However, it is strongly recommended to stay with the case chosen in the function definition. Typically functions use all-lowercase names.

### Arguments

When the function is invoked, the recorded `<commands>` are first modified by replacing formal parameters (`${arg1}`, ...) with the arguments passed, and then invoked as normal commands.

In addition to referencing the formal parameters you can reference the `ARGC` variable which will be set to the number of arguments passed into the function as well as `ARGV0`, `ARGV1`, `ARGV2`, ... which will have the actual values of the arguments passed in. This facilitates creating functions with optional arguments.

Furthermore, `ARGV` holds the list of all arguments given to the function and `ARGN` holds the list of arguments past the last expected argument. Referencing to `ARGV#` arguments beyond ARGC have undefined behavior. Checking that `ARGC` is greater than `#` is the only way to ensure that `ARGV#` was passed to the function as an extra argument.
