## Scripting Commands

### cmake_minimum_required

Require a minimum version of cmake.

```
cmake_minimum_required(VERSION <min>[...<policy_max>] [FATAL_ERROR])
```

### configure_file

Copy a file to another location and modify its contents.

https://blog.csdn.net/qq_38410730/article/details/103741579

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

### option

Provide a boolean option that the user can optionally select.

```
option(<variable> "<help_text>" [value])
```

https://www.cnblogs.com/Braveliu/p/15665143.html

### set

Set a normal, cache, or environment variable to a given value.

https://cmake.org/cmake/help/v3.28/command/set.html
https://blog.csdn.net/Calvin_zhou/article/details/104060927

## Project Commands

### add_compile_definitions

Add preprocessor definitions to the compilation of source files.

### add_compile_options

Add options to the compilation of source files.

### add_executable

Add an executable to the project using the specified source files.

```
add_executable(<name> [WIN32] [MACOSX_BUNDLE]
               [EXCLUDE_FROM_ALL]
               [source1] [source2 ...])
```

### add_library

Add a library to the project using the specified source files.

https://blog.csdn.net/fengbingchun/article/details/128160777

### add_link_options

Add options to the link step for executable, shared library or module library targets in the current directory and below that are added after this command is invoked.

### add_subdirectory

Add a subdirectory to the build.

```
add_subdirectory(source_dir [binary_dir] [EXCLUDE_FROM_ALL] [SYSTEM])
```

https://cmake.org/cmake/help/v3.28/command/add_subdirectory.html
https://blog.csdn.net/Dontla/article/details/129265306

### include_directories

Add include directories to the build.

```
include_directories([AFTER|BEFORE] [SYSTEM] dir1 [dir2 ...])
```

https://cmake.org/cmake/help/v3.28/command/include_directories.html

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

### target_link_libraries

Specify libraries or flags to use when linking a given target and/or its dependents.
