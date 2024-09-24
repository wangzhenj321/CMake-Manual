## cmake_parse_arguments

Parse function or macro arguments.

```
cmake_parse_arguments(<prefix> <options> <one_value_keywords>
                      <multi_value_keywords> <args>...)

cmake_parse_arguments(PARSE_ARGV <N> <prefix> <options>
                      <one_value_keywords> <multi_value_keywords>)
```

This command is for use in macros or functions. It processes the arguments given to that macro or function, and defines a set of variables which hold the values of the respective options.

### References

1. https://www.cnblogs.com/gaox97329498/p/10991449.html
