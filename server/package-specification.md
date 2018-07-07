# Package specification

Each package is identified by it's name and can have multiple versions. The latest version of a package is identified by the
`latest` keyword.

>This specification uses JSON as the format of interchangeable data.

## Description
This is the description of each field

| Field         	| Description                                                                	| Type     	| Required 	| Constraint                                                     	|
|---------------	|----------------------------------------------------------------------------	|----------	|----------	|----------------------------------------------------------------	|
| `name`        	| Name of the package                                                        	| `String` 	| ✔️        	| Max length 25                                                  	|
| `description` 	| Description of the package                                                 	| `String` 	| ✔️        	| Max length 200                                                 	|
| `alias`       	| Names used to identify this package. They have to be different from `name` 	| `Array`  	| ❌        	| Max elements 5. For each element, same constraint as `name` 	|

## Example

```json
{
   "name":"ypack",
   "description":"Multi-platform package manager",
   "alias":[
      "yp"
   ]
}
```
