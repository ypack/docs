# Package specification

Each package is identified by it's name and can have multiple versions. The latest version of a package is identified by the
`latest` keyword.

>This specification uses JSON as the format of interchangeable data.

## Description
This is the description of each field

| Field         	| Description                                                                	| Type        	| Required 	| Constraint                                                  	|
|---------------	|----------------------------------------------------------------------------	|-------------	|----------	|-------------------------------------------------------------	|
| `name`        	| Name of the package                                                        	| `String`    	| ✔️        	| Max length 25                                               	|
| `description` 	| Description of the package                                                 	| `String`    	| ✔️        	| Max length 200                                              	|
| `website`     	| Official website of the package                                            	| `String`    	| ✔️        	| Well formed URL                                             	|
| `alias`       	| Names used to identify this package. They have to be different from `name` 	| `Alias[]`  	| ❌        	| Max elements 5. For each element, same constraint as `name` 	|
| `authors`     	| List of package authors                                                    	| `Author[]`  	| ✔️        	| See [Author](#author)                                       	|
| `versions`    	| List of available versions for the package                                 	| `Version[]` 	| ✔️        	| See [Version](#version)                                     	|

### Author
Author detail info:

| Field         	| Description                                                                	| Type       	| Required 	| Constraint                                                  	|
|---------------	|----------------------------------------------------------------------------	|------------	|----------	|-------------------------------------------------------------	|
| `name`        	| Author name                                                        	| `String`   	| ✔️        	| Max length 50                                               	|
| `contact`        	| Author contact email                                                       	| `String`   	| ✔️        	| Well formed email                                              	|

### Version
Version details:

| Field      	| Description                           	| Type     	| Required 	| Constraint                                 	|
|------------	|---------------------------------------	|----------	|----------	|--------------------------------------------	|
| `name`     	| Version name                          	| `String` 	| ✔️        	| Max length 25                              	|
| `url`      	| Version url                           	| `String` 	| ✔️        	| Well formed URL                            	|
| `checksum` 	| Checksum of the downloadable resource 	| `String` 	| ❌        	|                                            	|
| `os`       	| Supported operating system version    	| `String` 	| ✔️        	| Can be `win`, `mac`, `ubuntu`              	|
| `arch`     	| Package architecture                  	| `String` 	| ✔️        	| Can be `x86-64`, `x86`, `ARMv6` or `ARMv8` 	|

### Alias
Alias detail info:

| Field         	| Description                                                                	| Type       	| Required 	| Constraint                                                  	|
|---------------	|----------------------------------------------------------------------------	|------------	|----------	|-------------------------------------------------------------	|
| `name`        	| Alias name                                                        	| `String`   	| ✔️        	| Max length 50                                               	|

## Example

```json
{
   "name":"ypack",
   "description":"Multi-platforma package manager",
   "alias":[
      {
         "name":"yp"
      }
   ],
   "website":"https://github.com/ypack",
   "authors":[
      {
         "name":"Javi",
         "contact":"hi@ypack.com"
      }
   ],
   "versions":[
      {
         "name":"1.0.0",
         "url":"https://github.com/ypack/releases/download/1.0.0/ypack-win.zip",
         "checksum":"85cc828a96735bdafcf29eb6291ca91bac846579bcef7308536e0c875d6c81d7",
         "os":"win",
         "arch":"x86-64"
      },
      {
         "name":"1.0.0",
         "url":"https://github.com/ypack/releases/download/1.0.0/ypack-ubuntu.tar.gz",
         "checksum":"",
         "os":"ubuntu",
         "arch":"x86"
      }
   ]
}
```
