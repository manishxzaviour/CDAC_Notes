- #[[java.lang.object class]]
- toString
	- is generally overriden to provide a string representation of the object state
- equals
	- acts like == by default {{cloze compare if the references are equal}}
	  checks if references point to same object
	- should be overloaded to check if states of two objects is equal
	- will return true even if the objects are different but have the same state
	- is a public non-static binary method
	- ```
	  Date x=new Date(1,1,2000);
	  Date y=new Date(1,1,2000);
	  (x.equals(y)) => true
	  ```
	- used with #instanceof and #getClass for cast validation
	- it is necessary to override the hashCode method also; as to maintain the general contract for the hashCode method that states that equal objects must have equal hash codes
	-
	-
- #getClass