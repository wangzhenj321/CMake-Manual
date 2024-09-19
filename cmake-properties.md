## Properties of Global Scope

- USE_FOLDERS

    Controls whether to use the FOLDER target property to organize targets into folders. The value of USE_FOLDERS at the end of the top level CMakeLists.txt file is what determines the behavior.

## Properties on Directories

- [INCLUDE_DIRECTORIES](./cmake-properties/Properties%20on%20Directories/INCLUDE_DIRECTORIES.md)

## Properties on Targets

- COMPILE_FEATURES

    Compiler features enabled for this target.

    The list of features in this property are a subset of the features listed in the `CMAKE_C_COMPILE_FEATURES`, `CMAKE_CUDA_COMPILE_FEATURES`, and `CMAKE_CXX_COMPILE_FEATURES` variables.

    Contents of `COMPILE_FEATURES` may use "generator expressions" with the syntax `$<...>`.

- CXX_STANDARD

    The C++ standard whose features are requested to build this target.

- CXX_STANDARD_REQUIRED

    Boolean describing whether the value of CXX_STANDARD is a requirement.

    If this property is set to ON, then the value of the CXX_STANDARD target property is treated as a requirement. If this property is OFF or unset, the CXX_STANDARD target property is treated as optional and may "decay" to a previous standard if the requested is not available.

- [INCLUDE_DIRECTORIES](./cmake-properties/Properties%20on%20Targets/INCLUDE_DIRECTORIES.md)

- [INTERFACE_INCLUDE_DIRECTORIES](./cmake-properties/Properties%20on%20Targets/INTERFACE_INCLUDE_DIRECTORIES.md)

## Properties on Tests

## Properties on Source Files

## Properties on Cache Entries

## Properties on Installed Files