## option

Provide a boolean option that the user can optionally select.

```
option(<variable> "<help_text>" [value])
```

If no initial `<value>` is provided, boolean OFF is the default value. If `<variable>` is already set as a normal or cache variable, then the command does nothing (see policy CMP0077).

In CMake project mode, a boolean cache variable is created with the option value. In CMake script mode, a boolean variable is set with the option value.

### References

1. https://www.cnblogs.com/Braveliu/p/15665143.html
