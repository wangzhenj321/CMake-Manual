## target_compile_features

Add expected compiler features to a target.

```
target_compile_features(<target> <PRIVATE|PUBLIC|INTERFACE> <feature> [...])
```

Specifies compiler features required when compiling a given target. If the feature is not listed in the `CMAKE_C_COMPILE_FEATURES`, `CMAKE_CUDA_COMPILE_FEATURES`, or `CMAKE_CXX_COMPILE_FEATURES` variables, then an error will be reported by CMake. If the use of the feature requires an additional compiler flag, such as `-std=gnu++11`, the flag will be added automatically.

The `INTERFACE`, `PUBLIC` and `PRIVATE` keywords are required to specify the scope of the features. `PRIVATE` and `PUBLIC` items will populate the `COMPILE_FEATURES` property of `<target>`. `PUBLIC` and `INTERFACE` items will populate the `INTERFACE_COMPILE_FEATURES` property of `<target>`. Repeated calls for the same `<target>` append items.

The named `<target>` must have been created by a command such as `add_executable()` or `add_library()` and must not be an ALIAS target.

Arguments to `target_compile_features` may use generator expressions with the syntax `$<...>`.
