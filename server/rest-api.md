# Server Rest API

Allowed methods for the `v1` group:

### Search packages by operating system

Retrieve a list of the 100 most popular packages ordered alphabetically by operating system. 
* **`/v1/packages?os=$OS`**
* `$OS` can be `win`, `mac` or `ubuntu`. See the [package specification](package-specification.md) for more info.
* Only returns the latest version of each package at the current time.

### Search package by name

Retrieve the package that matches with the given name and operating system.
* **`/v1/package?os=$OS&name=$NAME`**
* `$OS` can be `win`, `mac` or `ubuntu`. See the [package specification](package-specification.md) for more info.
* `$NAME` is the name of the package to search for.
* Returns the package with all available versions.

### Search latest package version by name

Retrieve the package that matches with the given name and operating system.
* **`/v1/package/latest?os=$OS&name=$NAME`**
* `$OS` can be `win`, `mac` or `ubuntu`. See the [package specification](package-specification.md) for more info.
* `$NAME` is the name of the package to search for.
* Returns the package with the latest available version at the current time.
