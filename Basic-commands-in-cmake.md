**Table of contents**
- [Examples](#examples)
- [add_definitions](#add_definitions)
- [add_executable](#add_executable)
- [add_library](#add_library)
- [add_subdirectory](#add_subdirectory)
- [cmake_minimum_required](#cmake_minimum_required)
- [find_library](#find_library)
- [find_package](#find_package)
- [include](#include)
- [include_directories](#include_directories)
- [install](#install)
- [message](#message)
- [project](#project)
- [set](#set)
- [target_link_libraries](#target_link_libraries)

## Examples

**DevCassons/CMakeLists.txt**

```cmake
cmake_minimum_required(VERSION 3.5)

project(DevCassons)

set(CMAKE_CXX_STANDARD 14)

# set(CMAKE_AUTOMOC ON)

if(YOCTO_SDK_DIR)
    # Using tookchain file, take headers from SDK
    set(CASSONS_LIB_INC_DIR "${TARGET_SYSROOT}/usr/include/libcassons")
else(YOCTO_SDK_DIR)
    add_definitions(-D__linux__)

    set(CMAKE_BUILD_TYPE "Debug")

    set(CMAKE_LIBRARY_PATH "/usr")
    find_library(CASSONS_LIB Cassons)
    if(NOT CASSONS_LIB)
        message(FATAL_ERROR "Cassons library hasn't been found")
    endif(NOT CASSONS_LIB)

    set(CASSONS_LIB_INC_DIR "${CMAKE_LIBRARY_PATH}/include/libcassons")
endif(YOCTO_SDK_DIR)

include_directories(
    ${CASSONS_LIB_INC_DIR}
)

include(GNUInstallDirs)
set(INSTALL_DIR ${CMAKE_BINARY_DIR}/install)
set(BIN_INSTALL_DIR ${INSTALL_DIR}/${CMAKE_INSTALL_BINDIR})

add_subdirectory(Heartbeat)
```

**DevCassons/Heartbeat/CMakeLists.txt**

```cmake
set(name "Heartbeat")                                                                                                      
                                                                                                                           
set(src                                                                                                                    
    main.cpp                                                                                                               
    Heartbeat.cpp                                                                                                          
)                                                                                                                          
                                                                                                                           
find_package(Boost COMPONENTS system filesystem QUIET REQUIRED)                                                            
find_package(Threads QUIET REQUIRED)                                                                                       
                                                                                                                           
add_executable(${name} ${src})                                                                                             
target_link_libraries(${name} ${CASSONS_LIB} ${Boost_FILESYSTEM_LIBRARY} ${Boost_SYSTEM_LIBRARY} ${CMAKE_THREAD_LIBS_INIT})
                                                                                                                           
install(                                                                                                                   
    TARGETS ${name}                                                                                                        
    RUNTIME DESTINATION ${BIN_INSTALL_DIR}                                                                                 
)                                                                                                                          
```

**DevCassons/YoctoToolchain.cmake**

```cmake
set(YOCTO_SDK_DIR "/opt/poky/2.4")
if (NOT "$ENV{YOCTO_SDK_DIR}" STREQUAL "")
    set(YOCTO_SDK_DIR "$ENV{YOCTO_SDK_DIR}")
endif ()

set(SYSROOTS_DIR "${YOCTO_SDK_DIR}/sysroots")
set(HOST_SYSROOT "${SYSROOTS_DIR}/x86_64-pokysdk-linux")
set(TARGET_SYSROOT "${SYSROOTS_DIR}/core2-32-poky-linux")

set(CROSS_COMPILE "i686-poky-linux")
set(CMAKE_SYSTEM_NAME Linux)

set(ENV{CC} "${HOST_SYSROOT}/usr/bin/${CROSS_COMPILE}/${CROSS_COMPILE}-gcc -m32 -march=core2 -mtune=core2 -msse3 -mfpmath=sse --sysroot=${TARGET_SYSROOT}")
set(ENV{CXX} "${HOST_SYSROOT}/usr/bin/${CROSS_COMPILE}/${CROSS_COMPILE}-g++ -m32 -march=core2 -mtune=core2 -msse3 -mfpmath=sse --sysroot=${TARGET_SYSROOT}")
set(CMAKE_FIND_ROOT_PATH ${TARGET_SYSROOT})
set(CMAKE_PREFIX_PATH ${TARGET_SYSROOT})

# search for programs in the build host directories
SET(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)

# for libraries and headers in the target directories
set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)

set (CMAKE_SKIP_RPATH TRUE)

set(OE_QMAKE_PATH_EXTERNAL_HOST_BINS ${HOST_SYSROOT}/usr/bin/qt5)
```

## [add_definitions](https://cmake.org/cmake/help/v3.10/command/add_definitions.html)
## [add_executable](https://cmake.org/cmake/help/v3.10/command/add_executable.html)
## [add_library](https://cmake.org/cmake/help/v3.10/command/add_library.html)
## [add_subdirectory](https://cmake.org/cmake/help/v3.10/command/add_subdirectory.html)
## [cmake_minimum_required](https://cmake.org/cmake/help/v3.10/command/cmake_minimum_required.html)
## [find_library](https://cmake.org/cmake/help/v3.10/command/find_library.html)
## [find_package](https://cmake.org/cmake/help/v3.10/command/find_package.html)

Load settings for an external project.

```cmake
find_package(<package> [version] [EXACT] [QUIET] [MODULE]
             [REQUIRED] [[COMPONENTS] [components...]]
             [OPTIONAL_COMPONENTS components...]
             [NO_POLICY_SCOPE])
```

Finds and loads settings from an external project. The `QUIET` option disables messages. The `REQUIRED` option stops processing with an error message if the package cannot be found.

## [include](https://cmake.org/cmake/help/v3.10/command/include.html)
## [include_directories](https://cmake.org/cmake/help/v3.10/command/include_directories.html)
## [install](https://cmake.org/cmake/help/v3.10/command/install.html)
## [message](https://cmake.org/cmake/help/v3.10/command/message.html)

```cmake
message([<mode>] "message to display" ...)
```

The optional `<mode>` keyword determines the type of message:
- ***(none)         = Important information***
- ***STATUS         = Incidental information***
- ***WARNING        = CMake Warning, continue processing***
- AUTHOR_WARNING = CMake Warning (dev), continue processing
- SEND_ERROR     = CMake Error, continue processing, but skip generation
- ***FATAL_ERROR    = CMake Error, stop processing and generation***
- DEPRECATION    = CMake Deprecation Error or Warning if variable CMAKE_ERROR_DEPRECATED or CMAKE_WARN_DEPRECATED is enabled, respectively, else no message.

## [project](https://cmake.org/cmake/help/v3.10/command/project.html)

The top-level *CMakeLists.txt* file for a project must contain a literal, direct call to the `project()` command; loading one through the `include()` command is not sufficient. If no such call exists CMake will implicitly add one to the top that enables the default languages (C and CXX).

## [set](https://cmake.org/cmake/help/v3.10/command/set.html)

#### Set Normal Variable

Set the given <variable> in the current function or directory scope.

```cmake
set(<variable> <value>... [PARENT_SCOPE])
```

#### Set Cache Entry

Set the given cache <variable> (cache entry).

```cmake
set(<variable> <value>... CACHE <type> <docstring> [FORCE])
```

It is possible for the cache entry to exist prior to the call but have no type set if it was created on the [cmake(1)](https://cmake.org/cmake/help/v3.10/manual/cmake.1.html#manual:cmake(1)) command line by a user through the `-D<var>=<value>` option without specifying a type.

#### Set Environment Variable

```cmake
set(ENV{<variable>} <value>...)
```

Set the current process environment <variable> to the given value.

## [target_link_libraries](https://cmake.org/cmake/help/v3.10/command/target_link_libraries.html)
