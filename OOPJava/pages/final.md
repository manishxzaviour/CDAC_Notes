## once initialized cannot be changed
- __modifier__
- using final keyword
  __variables, fields, methods, class__ 
  can be made as final
- ```
  final int n1;
  n1=10;
  :
  n1=20; //error as n1 cannot be reassigned
  ```
-
- can be initialized in
	- Declaration
	- #[[field initializer]]
	- #[[object initializer]]
	- #constructor
-
- can be initialized after declaration
-
- ### final reference
	- a final reference cannot be reassigned with another object
	- it will always point to the object it was initialized with. #this
	- ### objects cannot be finalized
	-