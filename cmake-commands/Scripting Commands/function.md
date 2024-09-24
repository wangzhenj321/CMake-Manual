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
