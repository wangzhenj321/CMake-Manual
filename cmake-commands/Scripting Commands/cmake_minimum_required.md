## cmake_minimum_required

Require a minimum version of cmake.

```
cmake_minimum_required(VERSION <min>[...<policy_max>] [FATAL_ERROR])
```

Sets the minimum required version of cmake for a project. Also updates the policy settings as explained below.

`<min>` and the optional `<policy_max>` are each CMake versions of the form `major.minor[.patch[.tweak]]`, and the `...` is literal.

If the running version of CMake is lower than the `<min>` required version it will stop processing the project and report an error.
