- when the relation between two classes is a has-a relation ship
- and may require  ___multiple instances___ of the same class
-
- #composition
	- when the dependency object is necessary for the instantiation __Tight Binding__
	- the dependency objected is created at instantiation itself
	- all objects of the dependent class will have the required instances of the dependencies
	- ```
	  class Depcy{
	  	...
	  }
	  class Depent{
	  	Depcy x = new Depcy();
	  	...
	  }
	  ```
	- the dependencies can be initialized in #[[field initializer]], #[[object initializer]], #constructor
-
-
-
- #aggregation
	- when the dependency object can be left out during instantiation __Loose binding__
	- the dependency object can be created as and when required
	- not all object will have the instances of dependency class
	- ```
	  class Depcy{
	  	...
	  }
	  class Depent{
	  	Depcy x = null;
	  	...
	      createDepcy(){
	      	this.x= new Depcy();
	      }
	  }
	  ```