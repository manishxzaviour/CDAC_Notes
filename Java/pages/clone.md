- in java assignment performs reference copy
- to have a independent copy of the object shallow or deep copy needs to be performed
- For coping the state of the object
	- each field needs to be copied and be independent
-
-
- ```
  Person p2=p1; //copy of reference; not independent
  p2=p1.clone();		
  ```
- > to perform clone on class object the type must implement the marker interface `Clonable`
  the clone method exists in the __Object__ class and requires the object be a instance of Clonable.
  >> the clone method is a __protected__ method of the Object class and can only be invoked in the class body only
- by default the `clone()` method performs shallow copy
- when a field is a reference to a pointer; `loosely coupled`, deep copy is needed
- to perform __deep copy__ the clone method needs to be __overriden__
	- by default the clone method is protected by overriding it can be made into public method
-
- ```
  class Date{...}
  class Person{
  	String name;
      Date dob;
      ...
  }
  Person p1= new Person("X",1,1,2000);
  Person p2=p1; // copy the reference
  Person p2= p1.clone(); // performs shallow  copy
  
  Person{
  	String name;
      Date dob;
  	Person(){
      	this.dob = new Date(); // to create a independent copy
      }
  	@override
      public Person clone(){
      	//return (Person) super.clone(); //narrowing // shallow copy
          Person temp = new Person();
          temp.name=this.name;
          temp.dob.day=this.dob.day;
          ...
          return temp;
      }
  }
  ```