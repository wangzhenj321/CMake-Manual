## configure_file

Copy a file to another location and modify its contents.

```
configure_file(<input> <output>
               [NO_SOURCE_PERMISSIONS | USE_SOURCE_PERMISSIONS |
                FILE_PERMISSIONS <permissions>...]
               [COPYONLY] [ESCAPE_QUOTES] [@ONLY]
               [NEWLINE_STYLE [UNIX|DOS|WIN32|LF|CRLF] ])
```

Copies an `<input>` file to an `<output>` file and substitutes variable values referenced as `@VAR@`, `${VAR}`, `$CACHE{VAR}` or `$ENV{VAR}` in the input file content. Each variable reference will be replaced with the current value of the variable, or the empty string if the variable is not defined.

### References

1. https://blog.csdn.net/qq_38410730/article/details/103741579