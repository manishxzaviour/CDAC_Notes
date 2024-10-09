- used to create implementations that will ~~theoretically~~ work with any data type
-
- Compile time polymorphism
-
- ```
  class Box{
  	Object item;
      Box(Object item){...}
      Object getItem(){...}
  }
  
  main - >
  Box b1 = new Box(new Integer(10));
  Integer x = (Integer)b1.getItem(); // returns type Object // downcasting // needs to be validated
  // __type unsafe__
  // will raise ClassCastException as casting will fail if the two are unrealated
  Box b2 = new Box(new String());
  Date y = (Date) b2; // will raise class cast exception
  ```
-
- Prior knowledge of the type at compile time; so that input types can be checked while performing operations
- before java 1.5 the Object class was used to provide genericity but is not casting safe.
-
- erasure
	- the structure of a generic only exists till compile time. is used to provide type safety till compile time.
	- after compile time all generics are erased and replaced with equivalent implementation of the Object class
	- this is called `erasure`
	- generics cannot function without later upcasting to object ref.
-
- > Standard Type names
  // for readability
  T - Type
  E - Entity
  K - Key
  V - Value
  N - Number
-
- ## generics
	- #generics/classes
		- ```
		  class Box<T>{
		  	private T object;
		      ...
		      T getItem(){retrun object;}
		  }
		  
		  main - >
		  Box<Integer> b1 = new Box<Integer>();
		  b1.setItem(new Integer(10));
		  // will accept objects of type Integer only
		  
		  Integer i = b1.getItem();
		  // no need to downcast
		  // __is type safe__
		  //types passed are checked at compile time
		  ```
	- #generics/methods
		- ```
		  class X{
		  	public static <T> void printBox(T obj){
		      	...
		      }
		  }
		  main - >
		  printBox(arr); // implicit
		  <String> printbox(arr); // explicit
		  ```
		- is a method having the above structure; any other type of definition is not considered as generic method
		- <T> returnType name(params){...}
		- `Difference between a generic method and method with unbounded parameter`
			- a generic method uses a generic typename to perform operations.
			  the implementation changes according to the type.
			- in method with unbounded parameter the reference type is resolved after call.
			  the implementation is common for all input and no typename is used
	- #generics/interface
		- __set of rules that work with any Type__
		- ```
		  interface Comparator<T>{
		  	compareTo(T obj){ // not a generic method
		      	..
		      }  // is a IMPORTANT interface
		      // retrurns -1,0,1 based on comparision of this object with the passed object
		      // is used to perform __natural sorting__ i.e based on unique fields
		  }
		  // used by Array.sort(T obj);
		  
		  interface Comparable<T>{
		  	compare(T obj1, T obj2){
		      	...
		      }
		      // -1, 0, 1
		      // is used to perform __non-natural sorting__
		  }
		  //used by Array.sort(T[] obj, new CustomComparator());
		  //Array.sort(T[] a, Comparator<? super T> c); 
		  // upper bound to block passing of objects whose fields are not visisble i.e sub-classes
		  // the comparator is generally a __local class__ as it is context specific and of no use elsewhere
		  ```
-
- __type inference__
	- types used can be detected automatically
	- ```
	  Box<Integer> b1 = new Box<>();
	  
	  // a generic reference can point to a raw type object
	  //Box<Integer> b1 = new Box();
	  // this is not a propper method
	  ```
-
- __type name used must be non-primitive__
	- reference type
-
- ### restrict the assignable classes using
	- ```
	  //un restricted
	  Box<Integer> b1 = new Box();
	  Box<Double> b2 = new Box();
	  Box<String> b3 = new Box();
	  // the type of object that can be accepted is not restricted
	  // e.g for a requirement of accepting only the Numbers and not strings
	  ```
	- __Bounded type__ Parameters
		- ```
		  class Box <T extends Number>{
		  	// will accept only of Number and its sub type objects
		      ...
		  }
		  //Box<String> = new Box<>(); // err
		  ```
		- ___used for objects only___
	- __Unbounded type__ parameters
		- ```
		  printBox(Box<?> b1){ //wildcard
		  	// will accept any type reference
		      sysout(b1.getObject())
		   }
		   main - > 
		  Box<Integer> b1 = new Box<>();
		  Box<String> b2 = new Box<>();
		  
		  printBox(b1); // passed reference
		  ```
		- __used for references only__
		- __do not have type checking on the reference__ #generics/Limitations
		- To allow only a range of reference types __Upper and Lower bounds__ are implements
		- ```
		  // upper bound
		  printBox(Box<? extends Number> b1){...}
		  // will only accept Number and its sub-class references only
		  
		  // lower bound
		  printBox(Box<? super Integer>){...}
		  //will accept Integer and its super-classes 
		  ```