The top-level *CMakeLists.txt* file for a project must contain a literal, direct call to the `project()` command; loading one through the include() command is not sufficient. If no such call exists CMake will implicitly add one to the top that enables the default languages (C and CXX).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk0MTUzOTA2Ml19
-->