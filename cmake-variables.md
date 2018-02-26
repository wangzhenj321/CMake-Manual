 1. **CMAKE_BINARY_DIR**
	
	The path to the top level of the build tree.
	
	This is the full path to the top level of the current CMake build tree. For an in-source build, this would be the same as **CMAKE_SOURCE_DIR**.
	
2. **CMAKE_SOURCE_DIR**
	
	The path to the top level of the source tree.
	
	This is the full path to the top level of the current CMake source tree. For an in-source build, this would be the same as **CMAKE_BINARY_DIR**.
	
3. **CMAKE_CURRENT_BINARY_DIR**
	
	The path to the binary directory currently being processed.
	
	This the full path to the build directory that is currently being processed by cmake. Each directory added by `add_subdirectory()` will create a binary directory in the build tree, and as it is being processed this variable will be set. For in-source builds this is the current source directory being processed.
	
4. **CMAKE_CURRENT_SOURCE_DIR**
	
	The path to the source directory currently being processed.
	
	This the full path to the source directory that is currently being processed by cmake.
	
5. **PROJECT_BINARY_DIR**
	
	Full path to build directory for project.
	
	This is the binary directory of the most recent `project()` command.
	
6. **PROJECT_SOURCE_DIR**
	
	Top level source directory for the current project.
	
	This is the source directory of the most recent `project()` command.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2ODc0NjA0MDNdfQ==
-->