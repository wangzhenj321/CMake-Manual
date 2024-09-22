## Variables that Provide Information

- CMAKE_CURRENT_BINARY_DIR

    The path to the binary directory currently being processed.

    This is the full path to the build directory that is currently being processed by cmake. Each directory added by `add_subdirectory()` will create a binary directory in the build tree, and as it is being processed this variable will be set. For in-source builds this is the current source directory being processed.

- CMAKE_CURRENT_SOURCE_DIR

    The path to the source directory currently being processed.

    This is the full path to the source directory that is currently being processed by cmake.

    When run in `cmake -P` script mode, CMake sets the variables `CMAKE_BINARY_DIR`, `CMAKE_SOURCE_DIR`, `CMAKE_CURRENT_BINARY_DIR` and `CMAKE_CURRENT_SOURCE_DIR` to the current working directory.

- CMAKE_MINIMUM_REQUIRED_VERSION

    The \<min\> version of CMake given to the most recent call to the `cmake_minimum_required(VERSION)` command in the current variable scope or any parent variable scope.

- CMAKE_PROJECT_NAME

    The name of the top level project.

    This variable holds the name of the project as specified in the top level CMakeLists.txt file by a `project()` command. In the event that the top level CMakeLists.txt contains multiple `project()` calls, the most recently called one from that top level CMakeLists.txt will determine the name that CMAKE_PROJECT_NAME contains.

- PROJECT_BINARY_DIR

    Full path to build directory for project.

    This is the binary directory of the most recent `project()` command.

- PROJECT_NAME

    Name of the project given to the project command.

    This is the name given to the most recently called `project()` command in the current directory scope or above. To obtain the name of the top level project, see the CMAKE_PROJECT_NAME variable.

-  PROJECT_SOURCE_DIR

    This is the source directory of the last call to the `project()` command made in the current directory scope or one of its parents. Note, it is not affected by calls to `project()` made within a child directory scope (i.e. from within a call to `add_subdirectory()` from the current scope).

## Variables that Change Behavior

- BUILD_SHARED_LIBS

    Global flag to cause `add_library()` to create shared libraries if on.

    If present and true, this will cause all libraries to be built shared unless the library was explicitly added as a static library. This variable is often added to projects as an `option()` so that each user of a project can decide if they want to build the project using shared or static libraries.

## Variables that Describe the System

## Variables that Control the Build

## Variables for Languages

- CMAKE_C_COMPILE_FEATURES

    List of features known to the C compiler

    These features are known to be available for use with the C compiler. This list is a subset of the features listed in the `CMAKE_C_KNOWN_FEATURES` global property.

- CMAKE_CXX_COMPILE_FEATURES

    List of features known to the C++ compiler

    These features are known to be available for use with the C++ compiler. This list is a subset of the features listed in the `CMAKE_CXX_KNOWN_FEATURES` global property.

- CMAKE_CXX_STANDARD

    Default value for CXX_STANDARD target property if set when a target is created.

- CMAKE_CXX_STANDARD_REQUIRED

    Default value for CXX_STANDARD_REQUIRED target property if set when a target is created.


## Variables for CTest

## Variables for CPack

## Variable Expansion Operators

- ENV

    Operator to read environment variables.

    Use the syntax `$ENV{VAR}` to read environment variable `VAR`.

    To test whether an environment variable is defined, use the signature `if(DEFINED ENV{<name>})` of the `if()` command.

## Internal Variables
