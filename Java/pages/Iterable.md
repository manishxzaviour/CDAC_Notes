- Interface inside java.lang
	- interface Iterable<T>
- represents a data structure that can be iterated over
- implements the #[[iterator method]]
- ```
  class X implements Iterable<X>{
  	class xIterator implements iterator{...} //override next and hasNext
  	@override
      public Iterator iterator(){
      	return new xIterator();
      }
  }
  ```
- All collections implement the Iterable interface
	- classes of the collection framework provide the implementation of the iterator method
-
- Implementing Iterable yields to Iterator
-
- > methods- 
  default void forEach(Customer <? super T> action)
  Iterator<T> iterator()
-