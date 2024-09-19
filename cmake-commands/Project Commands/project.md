## project

Set the name of the project.

### Synopsis

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

### Options

The options are:

- `VERSION <version>`

    Optional; may not be used unless policy CMP0048 is set to NEW.

    Takes a `<version>` argument composed of non-negative integer components, i.e. `<major>[.<minor>[.<patch>[.<tweak>]]]`, and sets the variables

    - `PROJECT_VERSION, <PROJECT-NAME>_VERSION`
    - `PROJECT_VERSION_MAJOR, <PROJECT-NAME>_VERSION_MAJOR`
    - `PROJECT_VERSION_MINOR, <PROJECT-NAME>_VERSION_MINOR`
    - `PROJECT_VERSION_PATCH, <PROJECT-NAME>_VERSION_PATCH`
    - `PROJECT_VERSION_TWEAK, <PROJECT-NAME>_VERSION_TWEAK`

    When the `project()` command is called from the top-level CMakeLists.txt, then the version is also stored in the variable `CMAKE_PROJECT_VERSION`.
