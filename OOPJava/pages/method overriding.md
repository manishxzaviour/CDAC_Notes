- done to provide a complete implementation when the super class provides
- - no implementation {{cloze abstract of interface}}
- - partial implementation
- - implementation that is different from needed
-
- for partial implementation
	- ```
	  Class Person{
	  	accept(){...}
	      display(){...}
	  }
	  Class Employee extends Person{
	  	accept(){.
	      		super.accept(); //unshadowing
	      ..}
	      display(){.
	      	super.display();
	      ..}
	  }
	  
	  ```
	- uses un #shadowing
-
- java supports #[[late binding]] only
   so the __overridden methods will be called only__
-
- #[[rules for method overriding]]
	- the overridden method will #shadowing 
	  logseq.order-list-type:: number
	- the visibility of the sub class method should be same or wider than the visibility of the super class implementation {{cloze protected-> public; default-> protected; static and private methods are not designed to be overridden}}
	  logseq.order-list-type:: number
	- the return type of the overridden method should be same or be a subclass of the return type of the super class implementation
	  logseq.order-list-type:: number
	- in overriding the sub class method #[[exception list]] should be same as that of the super class or should be a subset of it
	  logseq.order-list-type:: number
	- the [[@override]] annotation can be used to validate the override specifications