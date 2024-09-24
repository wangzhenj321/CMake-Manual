## find_package

Find a package (usually provided by something external to the project), and load its package-specific details.

### Basic Signature

```
find_package(<PackageName> [version] [EXACT] [QUIET] [MODULE]
             [REQUIRED] [[COMPONENTS] [components...]]
             [OPTIONAL_COMPONENTS components...]
             [REGISTRY_VIEW  (64|32|64_32|32_64|HOST|TARGET|BOTH)]
             [GLOBAL]
             [NO_POLICY_SCOPE]
             [BYPASS_PROVIDER])
```

Regardless of the mode used, a `<PackageName>_FOUND` variable will be set to indicate whether the package was found. When the package is found, package-specific information may be provided through other variables and Imported Targets documented by the package itself.

The `QUIET` option disables informational messages, including those indicating that the package cannot be found if it is not `REQUIRED`.

The `REQUIRED` option stops processing with an error message if the package cannot be found.

A package-specific list of required components may be listed after the `COMPONENTS` keyword. If any of these components are not able to be satisfied, the package overall is considered to be not found. If the `REQUIRED` option is also present, this is treated as a fatal error, otherwise execution still continues. As a form of shorthand, if the `REQUIRED` option is present, the `COMPONENTS` keyword can be omitted and the required components can be listed directly after `REQUIRED`.

### References

1. https://blog.csdn.net/zhanghm1995/article/details/105466372