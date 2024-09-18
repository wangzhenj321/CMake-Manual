## project

Set the name of the project.

```
project(<PROJECT-NAME> [<language-name>...])
project(<PROJECT-NAME>
        [VERSION <major>[.<minor>[.<patch>[.<tweak>]]]]
        [DESCRIPTION <project-description-string>]
        [HOMEPAGE_URL <url-string>]
        [LANGUAGES <language-name>...])
```

Sets the name of the project, and stores it in the variable `PROJECT_NAME`. When called from the top-level CMakeLists.txt also stores the project name in the variable `CMAKE_PROJECT_NAME`.

Also sets the variables:

- `PROJECT_SOURCE_DIR`, `<PROJECT-NAME>_SOURCE_DIR`

    Absolute path to the source directory for the project.

- `PROJECT_BINARY_DIR`, `<PROJECT-NAME>_BINARY_DIR`

    Absolute path to the binary directory for the project.

- `PROJECT_IS_TOP_LEVEL`, `<PROJECT-NAME>_IS_TOP_LEVEL`

    Boolean value indicating whether the project is top-level.

Further variables are set by the optional arguments described in the following. If any of these arguments is not used, then the corresponding variables are set to the empty string.
