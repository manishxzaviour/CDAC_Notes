- __Interface List<E>__
-
- is a ordered collection
-
- List is implemented by
	- ArrayList class
	- CopyOnWriteArrayList class
	- #LinkedList class class
	- Vector class
		- #Stack class
-
- #Vector
	- `Class Vector<E>`
	- indexed dynamic array
	- contains some pre collection i.e java 1.0 methods
	- is synchronized and #[[thread safe]]
	-
-
-
- ```
  List<Integer> = new ArrayList<>();
  ```
-
- > methods -
  boolean add(E e)
  void add(int index, E elements)
  boolean add(Collection<? extends E> c)
  void clear()
  boolean contains(Object o)
  boolean equals(Object o)
  E get(int index)
  int indexOf(Object o)
  boolean isEmpty()
  Iterator<E> iterator()
  int lastIndexOf(Object o)
  ListIterator<E> listIterator() // for reverse traversal
  E remove(Object o)
  E set(int index, E element) // set at position
  default void sort(Comparator<? super E>c)
  Object[] toArray()
-
- > for the contains(), indexOf() and remove() methods the equals() method is invoked internally
-
- List and all its sub-classes can be #traversal -ed using the index method