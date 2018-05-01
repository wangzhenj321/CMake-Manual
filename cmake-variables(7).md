[cmake-variables(7)](https://cmake.org/cmake/help/v3.10/manual/cmake-variables.7.html#manual:cmake-variables(7))

## Variables that Provide Information
1. ***CMAKE_BINARY_DIR***
2. ***CMAKE_CURRENT_BINARY_DIR***
3. ***CMAKE_CURRENT_LIST_DIR***
    
    Full directory of the listfile currently being processed.
    
    As CMake processes the listfiles in your project this variable will always be set to the directory where the listfile which is currently being processed (***CMAKE_CURRENT_LIST_FILE***) is located. The value has dynamic scope. When CMake starts processing commands in a source file it sets this variable to the directory where this file is located. When CMake finishes processing commands from the file it restores the previous value. Therefore the value of the variable inside a macro or function is the directory of the file invoking the bottom-most entry on the call stack, not the directory of the file containing the macro or function definition.
    
4. ***CMAKE_CURRENT_LIST_FILE***
5. ***CMAKE_CURRENT_SOURCE_DIR***
6. ***CMAKE_SKIP_RPATH***
7. ***CMAKE_TOOLCHAIN_FILE***
8. ***\<PROJECT-NAME\>_BINARY_DIR***
9. ***\<PROJECT-NAME\>_SOURCE_DIR***
10. ***PROJECT_BINARY_DIR***
11. ***PROJECT_SOURCE_DIR***

## Variables that Change Behavior
1. ***CMAKE_FIND_LIBRARY_PREFIXES***
2. ***CMAKE_FIND_LIBRARY_SUFFIXES***
3. ***CMAKE_FIND_ROOT_PATH***
4. ***CMAKE_FIND_ROOT_PATH_MODE_LIBRARY***
5. ***CMAKE_FIND_ROOT_PATH_MODE_PACKAGE***
6. ***CMAKE_FIND_ROOT_PATH_MODE_PROGRAM***
7. ***CMAKE_LIBRARY_PATH***
8. ***CMAKE_MODULE_PATH***
    
    ***;-list*** of directories specifying a search path for CMake modules to be loaded by the `include()` or `find_package()` commands before checking the default modules that come with CMake. By default it is empty, it is intended to be set by the project.

9. ***CMAKE_PREFIX_PATH***

    

10. ***CMAKE_SYSROOT***

## Variables that Describe the System
1. ***CMAKE_SYSTEM_NAME***

## Variables that Control the Build
1. ***CMAKE_AUTOMOC***

    Whether to handle `moc` automatically for Qt targets. This variable is used to initialize the ***AUTOMOC*** property on all the targets. See that target property for additional information.

2. ***CMAKE_AUTOUIC***

    Whether to handle `uic` automatically for Qt targets. This variable is used to initialize the ***AUTOUIC*** property on all the targets. See that target property for additional information.

3. ***CMAKE_INCLUDE_CURRENT_DIR***

    Automatically add the current source- and build directories to the include path.

    If this variable is enabled, CMake automatically adds ***CMAKE_CURRENT_SOURCE_DIR*** and ***CMAKE_CURRENT_BINARY_DIR*** to the include path for each directory. These additional include directories do not propagate down to subdirectories. This is useful mainly for out-of-source builds, where files generated into the build tree are included by files located in the source tree.

    By default `CMAKE_INCLUDE_CURRENT_DIR` is `OFF`.

## Variables for Languages
## Variables for CTest
## Variables for CPack
