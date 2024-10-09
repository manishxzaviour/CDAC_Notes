- Is a interface that declares the
- is a method of the #Iterable interface
- ```
  Iterator<T> iterator();
  ```
-
- Iterator deffers from enumirations as -
	- iterator allow the caller to remove elements from the underling collection during iteration #Iterator/fail_safe
- > methods -
  boolean hasNext()
  E next()
  default void remove() // remove last returned element
-
- Modification during iteration
	- #Iterator/fail_fast
		- iterators that fail {{cloze raise the ConcurrentModificationException}} when modifying the state of the underling collection during iteration
	- #Iterator/fail_safe
		- iterators that allow modification of the underling collection during iteration
	- state of the collection is the #hashCode it generates; the internal sequence can be changed but components cannot be added or removed
	- ```
	  Iterator itr = L1.iterator() // L1 is list
	  while(itr.hasNext()){
	  	if(itr.next()==30)
	      	itr.add(50)// will raise the exception as all iterators of the collection class are fail-fast
	  }
	  
	  List<Integer> L1 = new CopyOnWriteArray<>();
	  Iterator itr = L1.iterator(); // returns a fail-safe iterator 
	  // will allow modificaton during the iteration
	  //creates a copy for modification during the iteration
	  // once the iteration is completer the main loop is replaced by modified copy
	  ```
	- Iterator in java.util.Concurrent is fail-safe
-
- for reverse iteration the `ListIterator(int offset)` method can be used
	- provides the `hasPrevious()` and `previous()` methods
-