# Server Rest API

Allowed methods for the `v1` group:

### Search packages by operating system

Retrieve a list of the 100 most popular packages ordered alphabetically by operating system. 
* **`/v1/packages?os=$OS`**
* `$OS` can be `win`, `mac` or `ubuntu`. See the [package specification](package-specification.md) for more info.
* Only return the latest version of each package.
