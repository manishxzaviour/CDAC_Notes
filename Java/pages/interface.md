- implemented in java 1.7 for avoidance of
- ## fragile base class problem
	- when a change is made in a super class like addition of a abstract method:
	  all the sub classes need to override the abstract method and be __recompiled__
	- this requires __changes in existing codebase__ which is undesirable
-
- Interfaces are designed to solve this
	- a interface is supposed to be `designed only once`
	- any additional functionality is to be added in another interface
	- if newer behavior is required it can be added to another interface
	- and __any subclasses that require this behaviour can implement this new interface__
	- modification and recompilation of the subclasses that require this method can be done alone
-
- ### provide set of protocols/ specification that every class that implements it has to follow
- #### an interface should preferably be atomic to provide reusability and avoid fragile base class problem
-
- ```
  interface Acceptable{ // the identifier should generally be a adjective
  	void accept(Scanner s);
  }
  
  class Employee extends Person implements Acceptable{
  	:
  }
  ```
- a interface includes abstract methods only
- the methods declared are `public abstract` by default
-
- a class can __extend to other and implement interface__ in that sequence only
	- NOT class c1 implements i1 extends c2
	- ```
	  interface i1{}
	  interface i2{}
	  class c1{}
	  class c2{}
	  
	  //valid
	  	c1 extends c2
	      c1 implements i1
	      c1 implements i1,i2
	  //invalid
	  	c1 implements c1
	  	c1 extends i1
	      c1 extends c1,c2
	  ```
-
- can be used to keep __method design common across unrelated classes__ as well
	- ```
	  interface Acceptable{...}
	  interface Displayable{...}
	  
	  class Time implements Acceptable{
	  	@override
	      public void accept(Scanner s){...}
	  }
	  class Employee implements Acceptable, Displayable{
	  	@override
	      public void accept(Scanner s){...}
	  }
	  ```
-
-
- > all interfaces are compiled in their own class files
  a reference of type interface can be created
  instantiation is not possible
  a interface can have final static data members // like global constants
	- ```
	  interface x{
	  	int x=10; // public static final int x=10;
	  }
	  ```
-
- a reference of a interface can store classes that implement it. 
  it can be used for __upcasting of unrelated classes__
	- ```
	  interface X{...}
	  class a implements X{...}
	  class b implements X{...}
	  X ref=a;
	  X ref2=b;
	  
	  interface Y{...}
	  
	  class p implements X,Y{...}
	  
	  X ref3 = p;
	  Y ref4= (Y) ref3 // NOT DOWNCASTING BUT TYPE CONVERSION 
	  // ref3 MUST HAVE IMPLEMENTED X AND Y
	  ```
-
-
- EG
	- ```
	  in java 
	  class implements Instantiable;
	  abstract class and interface do not
	  ```
-
-
- to keep the method design same the __identifiers__ of the #[[abstract method]] should be __logical and generic__
-
- multiple inheritance of interfaces is allowed in java
-
-
- ### Java 1.8 v interfaces
- to avoid recompilation after introducing and implementing new interfaces;
  to have additional behaviour
- to call a new method implemented for the new interface - the reference used (upcasting) will need to be changes to become of the new interface type
- for language advantages
- ```
  Shape{...} // area, accept
  Circle implements Shape {...}
  Rectangle implements Shape{...}
  Sqaure implements Shape{...}
  main{
  	Shape c = new Circle();
  }
  
  // new update
  // to add ability to calcuate perimeter for rectangle
  // before j v1.8
  
  interface ShapePeri{
  	calcPeri();
  }
  Rectangle implements Shape, ShapePeri{
  	calcPeri(){...}
  }
  main{
  	ShapePeri r = new Rectangle();
      
      // validation
      if(r instanceof ShapePeri)
      	r.calcPeri();
  }
  ```
-
- prior to j v1.8 when a interface was to be created for addition functionality all sub classes would need to implement the new method and all references would need to be changed to that of the new interface to access this new method.
- __fragile base class problem__
-
- to avoid such redundancy -
	- interfaces can have `default` methods with certain implementation within the interface itself.
	- the subclasses are __not forced__ to provide implementation for a default function
	- the method implementation is inherited into all subclasses who can override it.
	- the default method can have a partial implementation or a fallback one.
	- ```
	  interface Shape{
	  	:
	  	default void calcPeri(){
	      	sysout("implementation not provided");
	      }
	  }
	  main{
	  	Shape rect = new Rectangle();
	      rect.calcPeri(); // implementaion overrided
	      Shape circle = new Circle();
	      circle.calcPeri(); // no override // default method
	  }
	  ```
	- no need for type conversation or validation
	- the dependent types just need to override the default method.
	- others can have no implementation.
		- on call on such objects the default implementation will be executed
-
- a interface can also contain static methods called `Helper methods`
	- this negates the need for separate helper class (like Collections class)
	- e.g static method shapeFactory can be implemented in the Shape interface itself.
	- called on `InterfaceName.method()`
-
- __Cons__
	- when default methods are defined, if two different interfaces implement default method with the same name, signature - a diamond problem may occur
	- so implementation of such two interfaces is not allowed. when multiple methods are inherited `redefinition` occurs
	- if the class itself overrides the method, its method will be called and no diamond problem will occur.
-
- a default method can be reused in the overridden method to provide partial implementation.
	- > InterfName.super.method();  call
	- as multiple inheritance is possible and multiple default methods can exist the Interface name is used to identify the super class method
	- if the super class method is changed to have `default` access specifier;__the super method cannot hide the interface method__
	-