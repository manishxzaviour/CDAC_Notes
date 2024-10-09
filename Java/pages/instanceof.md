- binary operator to validate before #downcasting
- returns a booliean value
	- true if instance of class
	- false if the class is null
-
- ```
  Date x;
  (x instanceof Date) => true
  (x instance of Employee) => false
  (null instance of Date) => false
  
  object instanceof type
  ```
-
- before casting the instanceof check should always be used to avoid the #ClassCastException
-
- works to check a is-a relation ship
- - __will return true if the object is an instance of a subclass of the type__
- - __true if the type is a interface and the object implements it__
-
- ___cannot be used if there is no relationship between the object that is being compared and the type___
	- will generate compile time error
-
-
- like using #getClass method of the #[[object class]]
-