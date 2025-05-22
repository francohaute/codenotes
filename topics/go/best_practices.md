
# Package level

## Init Function

You should avoid the init function whenever is possible. Mostly it's use for 
initializing package-level variables that can't be configured in a single assignment.

When you need to initialize and declare a package level variable that is meant 
to be modified, it is advise to put it in a struct and initialized it and modify 
it by functions in the package.


```go
var number int


```
