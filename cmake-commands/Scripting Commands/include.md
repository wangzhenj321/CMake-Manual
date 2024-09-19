## include

Load and run CMake code from a file or module.

```
include(<file|module> [OPTIONAL] [RESULT_VARIABLE <var>]
                      [NO_POLICY_SCOPE])
```

Loads and runs CMake code from the file given. Variable reads and writes access the scope of the caller (dynamic scoping). If `OPTIONAL` is present, then no error is raised if the file does not exist. If `RESULT_VARIABLE` is given the variable `<var>` will be set to the full filename which has been included or `NOTFOUND` if it failed.

### References

1. https://github.com/eglinuxer/study_cmake/blob/main/doc/019_cmake_include.md
