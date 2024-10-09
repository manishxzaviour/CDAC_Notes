- implements Queue
- __Double ended Queue__
-
- implemented by
	- #LinkedList
	- #ArrayDeque
-
- Has a `Head` and `Tail`
-
- > methods - 
  offerFirst(e)
  peekFirst(e)
  pollFirst(e)
  // same for last
-
- using the Deque collection both `sack` and `queue` can be implemented
	- // a `Queue` can be implemented by inserting on last and retrieving on first
	- ```
	  Deque<Integer> q1 = new Deque<>();
	  //FIFO
	  q1.offerLast(10);
	  q1.offerLast(20);
	  sysout(q1.pollFirst()); // 10
	  sysout(q1.pollFirst()); // 20
	  
	  ```
	- // a `Stack` can be implemented by inserting and retrieving on one particular end
	  ```
	  Deque<Integer> q1 = new Deque<>();
	  //LIFO
	  q1.offerLast(10);
	  q1.offerLast(20);
	  sysout(q1.pollLast()); // 20
	  sysout(q1.pollLast()); // 10
	  ```
-