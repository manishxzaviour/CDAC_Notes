- when a class contains pointers and dynamic memory is allocated [[shallow copy]] causes copy of the value of the pointer i.e its pointed memory instead of the actual pointed value
- to perform proper copy of this type the copy constructor needs to be defined to perform deep copy
- the value at the allocated memory location is copied to new allocated memory inside of copied object
- thus the two objects are independent