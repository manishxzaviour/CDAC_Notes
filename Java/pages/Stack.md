- extends vector
- introduced in java 1.0
- synchronized as vector is synchronized
- defines the __LIFO__ behaviour
- > methods -
  push(e)
  E pop()
  boolean empty()
  E peek()
- ```
  Stack<Integer>= new Stack<>(); // upcasting is redundant as all important behaviours are implemented by stack [slicing]
  ```
-
- A more complete and consistent LIFO stack is implemeted in #Deque
	- __prefer deque over stack__