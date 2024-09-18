## Scripting Commands

- [cmake_minimum_required](./cmake-commands/Scripting%20Commands/cmake_minimum_required.md)

    Require a minimum version of cmake.

### cmake_policy

Manage CMake Policy settings.

- [configure_file](./cmake-commands/Scripting%20Commands/configure_file.md)

    Copy a file to another location and modify its contents.

### find_package

Find a package (usually provided by something external to the project), and load its package-specific details.

https://blog.csdn.net/zhanghm1995/article/details/105466372
https://cmake.org/cmake/help/v3.28/command/find_package.html

### get_filename_component

Get a specific component of a full filename.

https://cmake.org/cmake/help/v3.28/command/get_filename_component.html

### include

Load and run CMake code from a file or module.

### list

Operations on semicolon-separated lists.

https://www.cnblogs.com/Braveliu/p/15820627.html

### message

Log a message.

- [option](./cmake-commands/Scripting%20Commands/option.md)

    Provide a boolean option that the user can optionally select.

- [set](./cmake-commands/Scripting%20Commands/set.md)

    Set a normal, cache, or environment variable to a given value.

## Project Commands

### add_compile_definitions

Add preprocessor definitions to the compilation of source files.

### add_compile_options

Add options to the compilation of source files.

- [add_executable](./cmake-commands/Project%20Commands/add_executable.md)

    Add an executable to the project using the specified source files.

- [add_library](./cmake-commands/Project%20Commands/add_library.md)

    Add a library to the project using the specified source files.

### add_link_options

Add options to the link step for executable, shared library or module library targets in the current directory and below that are added after this command is invoked.

- [add_subdirectory](./cmake-commands/Project%20Commands/add_subdirectory.md)

    Add a subdirectory to the build.

- [include_directories](./cmake-commands/Project%20Commands/include_directories.md)

    Add include directories to the build.

- [project](./cmake-commands/Project%20Commands/project.md)

    Set the name of the project.

- [target_compile_definitions](./cmake-commands/Project%20Commands/target_compile_definitions.md)

    Add compile definitions to a target.

- [target_include_directories](./cmake-commands/Project%20Commands/target_include_directories.md)

    Add include directories to a target.

- [target_link_libraries](./cmake-commands/Project%20Commands/target_link_libraries.md)

    Specify libraries or flags to use when linking a given target and/or its dependents.
