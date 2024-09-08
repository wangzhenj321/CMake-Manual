## Scripting Commands

### cmake_minimum_required

Require a minimum version of cmake.

```
cmake_minimum_required(VERSION <min>[...<policy_max>] [FATAL_ERROR])
```

### find_package

Find a package (usually provided by something external to the project), and load its package-specific details.

### get_filename_component

Get a specific component of a full filename.

https://cmake.org/cmake/help/v3.28/command/get_filename_component.html

### include

Load and run CMake code from a file or module.

### list

Operations on semicolon-separated lists.

https://www.cnblogs.com/Braveliu/p/15820627.html

### option

Provide a boolean option that the user can optionally select.

```
option(<variable> "<help_text>" [value])
```

https://www.cnblogs.com/Braveliu/p/15665143.html

### set

Set a normal, cache, or environment variable to a given value.

https://cmake.org/cmake/help/v3.28/command/set.html

## Project Commands

### add_library

Add a library to the project using the specified source files.

### add_subdirectory

Add a subdirectory to the build.

```
add_subdirectory(source_dir [binary_dir] [EXCLUDE_FROM_ALL] [SYSTEM])
```

https://cmake.org/cmake/help/v3.28/command/add_subdirectory.html
https://blog.csdn.net/Dontla/article/details/129265306

### project

Set the name of the project.

```
project(<PROJECT-NAME> [<language-name>...])
project(<PROJECT-NAME>
        [VERSION <major>[.<minor>[.<patch>[.<tweak>]]]]
        [DESCRIPTION <project-description-string>]
        [HOMEPAGE_URL <url-string>]
        [LANGUAGES <language-name>...])
```

Sets the name of the project, and stores it in the variable PROJECT_NAME. When called from the top-level CMakeLists.txt also stores the project name in the variable CMAKE_PROJECT_NAME.

Also sets the variables:

- PROJECT_SOURCE_DIR, \<PROJECT-NAME\>_SOURCE_DIR

    Absolute path to the source directory for the project.

- PROJECT_BINARY_DIR, \<PROJECT-NAME\>_BINARY_DIR

    Absolute path to the binary directory for the project.
