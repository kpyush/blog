## Storage classes in C:
##### Static
* variable used inside a function preserve their values even after they are out of scope.
* global variables can be used by functions of that file only.
* global variables are initiased with value 0.
* static functions can not be used by functions in another file.
##### Extern
* Variables can be accessed by any other file in the project.
* Variable dependancy is resolved by the linker.
##### Auto
* It is the default storage class for all the varibales
* their scope is limited to a block/function in which they are declared.
* they are assigned garbage value wherever they declared. 
##### Register
