- points to the address of a object in heap memory
- is a variable that is allocated size
- are declared with specific type which determines the methods and fields that can be accessed through it
- unlike cpp the object pointed by a reference can be changed
- only the address to the object is stored
-
- during assignment the address of the object is copied and not the object itself
- ```
  Time t1; //t1 is a reference of type Time
  t1=new Time(); 
  Time t2;
  t2=t1; //copy of address t2 gets its own address to the object and does not point through t1
  ```
-
- in  case of reference of a #primitives wrapper assignment allways returns value
- w.r.t objects the reference will copy the address of the object
-
- thus in java `pass by reference` is available for objects only {{cloze java design philisophy; no requirement to pass references to variables as there is no global primitives and the dynamically allocated primitives perform auto #boxing and #unboxing }}
-
- __Nothing in java is passed by reference. all is pass by value__
- when passing a reference its value is coppied