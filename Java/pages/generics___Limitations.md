- cannot instantiate generic type with primitive types. __only reference types allowed__
  logseq.order-list-type:: number
	- logseq.order-list-type:: number
	  ```
	  Array<int> ... //err
	  Array<Integer> ... //no-err
	  ```
- cannot create instance of the type parameter
  logseq.order-list-type:: number
	- logseq.order-list-type:: number
	  ```
	  T obj = new T();
	  ```
- cannot declare static fields with generic type parameters
  logseq.order-list-type:: number
	- logseq.order-list-type:: number
	  ```
	  static T object; // err
	  ```
- __cannot use casts or instanceof__
  logseq.order-list-type:: number
- cannot create arrays
  logseq.order-list-type:: number
- cannot create, catch or throw objects of type
  logseq.order-list-type:: number
- cannot overload a method by changing its generic type. 
  logseq.order-list-type:: number
  Because after erasing/removeing the type param, if signature of two methods is same it will cause compile time err
	- logseq.order-list-type:: number
	  ```
	  printBox(Box<Integer> b){...};
	  printBox(Box<Double> b){...};
	  ```