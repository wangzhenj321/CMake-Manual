# cmake

## Synopsis

```
Generate a Project Buildsystem
 cmake [<options>] -B <path-to-build> [-S <path-to-source>]
 cmake [<options>] <path-to-source | path-to-existing-build>

Build a Project
 cmake --build <dir> [<options>] [-- <build-tool-options>]

Install a Project
 cmake --install <dir> [<options>]

Open a Project
 cmake --open <dir>

Run a Script
 cmake [-D <var>=<value>]... -P <cmake-script-file>

Run a Command-Line Tool
 cmake -E <command> [<options>]

Run the Find-Package Tool
 cmake --find-package [<options>]

Run a Workflow Preset
 cmake --workflow [<options>]

View Help
 cmake --help[-<topic>]
```

## Description

The `cmake` executable is the command-line interface of the cross-platform buildsystem generator CMake.

## Introduction to CMake Buildsystems

A buildsystem describes how to build a project's executables and libraries from its source code using a build tool to automate the process. For example, a buildsystem may be a Makefile for use with a command-line `make` tool or a project file for an Integrated Development Environment (IDE).

In order to avoid maintaining multiple such buildsystems, a project may specify its buildsystem abstractly using files written in the CMake language. From these files CMake generates a preferred buildsystem locally for each user through a backend called a generator.

To generate a buildsystem with CMake, the following must be selected:

- Source Tree

    The top-level directory containing source files provided by the project.

- Build Tree

    The top-level directory in which buildsystem files and build output artifacts (e.g. executables and libraries) are to be stored. CMake will write a CMakeCache.txt file to identify the directory as a build tree and store persistent information such as buildsystem configuration options.

- Generator

    This chooses the kind of buildsystem to generate.

## Generate a Project Buildsystem

Run CMake with one of the following command signatures to specify the source and build trees and generate a buildsystem:

- `cmake [<options>] -B <path-to-build> [-S <path-to-source>]`
- `cmake [<options>] <path-to-source>`
- `cmake [<options>] <path-to-existing-build>`

### Options

- `-S <path-to-source>`

    Path to root directory of the CMake project to build.

- `-B <path-to-build>`

    Path to directory which CMake will use as the root of build directory.

    If the directory doesn't already exist CMake will make it.

- `-D <var>:<type>=<value>, -D <var>=<value>`

    Create or update a CMake CACHE entry.

## Build a Project

## Install a Project

