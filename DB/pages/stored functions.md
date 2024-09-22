- #parameters
- is a #[[stored object]]
-
- ```
  mysql> set x=pqr();
  ```
	- a function cannot be called by itself as it returns a value that needs to be stored
	- it can be called only if it is assigned to or used in an expression
-
- stored in compiled format
-
- recursion and nested calls is allowed
-
- overloading is not allowed
-
- __can have #IN only not any other #parameters__
-
- [[types of functions]]
-
- ```
  delimiter //
  create function abc()
  returns int
  deterministic
  begin
  	return 10;
  end;
  delimiter ; 
  ```
-
- show all functions and definitions
	- ```
	  show create functions;
	  ```
- grant
	- ```
	  grant execute on classwork.abc to amit@host;
	  ```