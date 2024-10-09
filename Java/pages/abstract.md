- `abstract` keyword
- used to define #[[abstract class]] and #[[abstract method]]
- __[[abstract method]]__
	- a method declared as abstract has __no defination__
	  and only a declearation
	- a abstract method is meant to be overridden in the sub-classes
	- any sub-class that does not provide the implementation of the abstract method will become a #[[abstract class]] itself
- __[[abstract class]]__
	- a class that contains atleast one abstract method becomes an abstract class
	- a abstract class cannot be instantiated anywhere other than its sub-classes
	- it may consist of constructor, methods and fields
-
- a abstract method should be a common method that is applicable to all sub-classes
	- all concrete sub-class must have implementation of the abstract methods
- ```
  public abstract class Super{
  	public abstract void calcTotalSal();
  }
  ```
-
- abstract classes are used to provide a structure for design of similar subclasses
	- the sub classes may have one or more similar behavior
-
- a abstract class is extendable #inheritance