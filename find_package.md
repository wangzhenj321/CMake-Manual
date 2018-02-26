Load settings for an external project.
```cmake
find_package(<package> [version] [EXACT] [QUIET] [MODULE]
             [REQUIRED] [[COMPONENTS] [components...]]
             [OPTIONAL_COMPONENTS components...]
             [NO_POLICY_SCOPE])
```
Finds and loads settings from an external project. The `QUIET` option disables messages. The `REQUIRED` option stops processing with an error message if the package cannot be found.

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEwNjUwMDM1MV19
-->