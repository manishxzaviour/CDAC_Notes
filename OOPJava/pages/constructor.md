- same name as class
- no return type
- initialize state of object
- called on object creation automatically
- constructor
	- parameterless
	- parameterized
-
- the constructor must be a public method
- #[[Constructor chaining]]
	- constructor deligation
	- a constructor of a class can call the constructor of the same class that has different parameter
	- done to support reusability
	- ```
	  public Date(){
	  	this(3,1,2000);
	  }
	  public Date(int day, int month, int year){
	  	this.day=day;
	      this.month=month;
	      this.year=year;
	  }
	  ```
-
- #[[field initializer]]
- #[[object initializer]]
- #[[static initializer]]
- no support for #[[default parameters]]
-
- __execution sequence__
	- field initializer
	  logseq.order-list-type:: number
	- object initializer
	  logseq.order-list-type:: number
	- constructor
	  logseq.order-list-type:: number