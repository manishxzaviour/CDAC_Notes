- the static and non-static members are stored on the method area only once. 
  when a function is called through the object these functions are referred.
  To access the state identity of calling object the this reference is used
- the this reference is a #final reference and refers to the object memory in heap
- ```
  Time t2=new Time();
  t.accept(); 
  //accept(t); 
  //accept(final Time this);
  ```
-
- ### the this pointer is passed to the non-static members only
-
- inside the class declaration the members can be accessed using the ' . ' operator
-
- #[[this statement]]
	- when performing #[[Constructor chaining]]
	- this(params);
	- __the this statement must be on the first line of the constructor defination__