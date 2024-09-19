## Introduction

## Whitespace And Quoting

## Debugging

Since generator expressions are evaluated during generation of the buildsystem, and not during processing of CMakeLists.txt files, it is not possible to inspect their result with the `message()` command.

One possible way to generate debug messages is to add a custom target:

```
add_custom_target(genexdebug COMMAND ${CMAKE_COMMAND} -E echo "$<...>")
```

After running cmake, you can then build the `genexdebug` target to print the result of the `$<...>` expression (i.e. run the command `cmake --build ... --target genexdebug`).

Another way is to write debug messages to a file with `file(GENERATE)`:

```
file(GENERATE OUTPUT filename CONTENT "$<...>")
```

## Generator Expression Reference

### Conditional Expressions

A fundamental category of generator expressions relates to conditional logic. Two forms of conditional generator expressions are supported:

- `$<condition:true_string>`

    Evaluates to `true_string` if `condition` is 1, or an empty string if `condition` evaluates to 0. Any other value for `condition` results in an error.

- `$<IF:condition,true_string,false_string>`

    Evaluates to `true_string` if `condition` is 1, or `false_string` if `condition` is 0. Any other value for `condition` results in an error.

Typically, the `condition` is itself a generator expression. For instance, the following expression expands to `DEBUG_MODE` when the `Debug` configuration is used, and the empty string for all other configurations:

```
$<$<CONFIG:Debug>:DEBUG_MODE>
```

Boolean-like `condition` values other than 1 or 0 can be handled by wrapping them with the `$<BOOL:...>` generator expression:

- `$<BOOL:string>`

    Converts `string` to 0 or 1. Evaluates to 0 if any of the following is true:

    - `string` is empty,
    - `string` is a case-insensitive equal of 0, FALSE, OFF, N, NO, IGNORE, or NOTFOUND, or
    - `string` ends in the suffix -NOTFOUND (case-sensitive).

    Otherwise evaluates to 1.

The `$<BOOL:...>` generator expression is often used when a `condition` is provided by a CMake variable:

```
$<$<BOOL:${HAVE_SOME_FEATURE}>:-DENABLE_SOME_FEATURE>
```

### Logical Operators

The common boolean logic operators are supported:

- `$<AND:conditions>`

    where `conditions` is a comma-separated list of boolean expressions, all of which must evaluate to either 1 or 0. The whole expression evaluates to 1 if all conditions are 1. If any condition is 0, the whole expression evaluates to 0.

- `$<OR:conditions>`

    where `conditions` is a comma-separated list of boolean expressions. all of which must evaluate to either 1 or 0. The whole expression evaluates to 1 if at least one of the `conditions` is 1. If all `conditions` evaluate to 0, the whole expression evaluates to 0.

- `$<NOT:condition>`

    `condition` must be 0 or 1. The result of the expression is 0 if `condition` is 1, else 1.

### Primary Comparison Expressions

### Toolchain And Language Expressions

#### Compiler Language And ID

- `$<COMPILE_LANG_AND_ID:language,compiler_ids>`

    1 when the language used for compilation unit matches `language` and CMake's compiler id of the `language` compiler matches any one of the comma-separated entries in `compiler_ids`, otherwise 0.
