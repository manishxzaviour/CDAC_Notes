-
- provides sorted storage
	- based on hash table
-
- ```
  PriorityQueue<Integer> i = new PriorityQueue<>()
  i.add(10);
  i.add(20);
  i.add(40);
  i.add(15);
  
  sysout(i) // 10, 15, 20, 40
  ```
-
- provides natural ordering  by default
- can store based on comparator provided in constructor
	- ```
	  PriorityQueue(Comparator<? extends E> c);
	  ```
-
- If a non-comparable element is inserted in a priorityqueue poll and peek methods will throw a `ClassCastException` as the `compareTo` is called internally.
-
- In a priorityQueue the __least priority element will be at the tail__ of the queue
-
- used to <u><b>Process high priority elements first</b></u>.
-