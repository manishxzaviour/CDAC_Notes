### represents pipeline of operations through witch data is processed
-
- a stream pipeline can contain multiple operations from one end to the other
-
- follows #functional_programming ; implemented in java v 1.8
-
- Stream operations
	- intermediate
		- __generate another stream as output__
		- stateless operations
			- filter(), map(), flatMap(), skip()
			- operations that pass the element immediately after recieving it
		- stateful operations
			- sorted(), distinct()
			- operations that store the elements until the previous process is exhausted and then begins processing
	- terminal
		- __generate some output not stream__
		- reduce(), forEach(), collect(), toArray(), count(), max(), min()
	- take functional interface implementations as args
-
- stream does not provide any storage beyond its operation
- no operation changes the stream itself. a new stream is created each time.
- __stream is evaluated only if a terminal operation is performed.__
- stream that processes a terminal operation cannot be processed again.
-
- >a stream can be created using - 
  stream() method of Collection interface and Arrays
  and
  of() 
  generate()
  iterate()
  empty()
  static methods from the Stream method
  #NIO file class
	-
-
-
- ```
  List<Integer> l1 = new ArrayList<>();
  l1.stream().forEach(sysout); //method reference
  
  Stream<Integer> s1 = Sream.of(l1); // not recomended as s1 cannot be used after processing once
  
  s1 = Stream.generate(
  	()->10 // supplier ()->T
  ).limit(10);
  // will generate a infinite stream that is limited to 10 values
  // using a constant return value;
  
  s1= Stream.iterate(1,i->i+1).limit(10);
  // generate infinite stream that can have varying value based on given seed value (1)
  
  List<String> l1 = new ArrayList<>();
  Collections.addAll(l1, "abc","axt","pqe","pasad","wqrqq","qwqw","q","qwdqe");
  
  Stream.of(l1).forEach(sysout); // display all 
  // terminal
  
  .fiter() // filter based on return form Predicate functional interface test method
  Stream.of(l1).filter(
  	(e)-> e.biginsWith('a');
  ); 
  // intermediate and stateless
  
  .map( //filter based on apply from Function interface
  	s->s.toUpperCase()
  )
   // intermediate and stateless
   
   .sorted( // sort based on natural order or a comparator
   	(x,y)->{y.compareTo(x);}
   )
   // intermediate and statefull
  
  .skip(10) // skip first 10 elements
  // intermediate and stateless
  
  .limit(10) //limit the pipeline cycle to 10 elemnts
  // intermediate stateless
  
  .distinct() // pass only distinct values
  // intermediate and statefull
  
  .count() // count the no of elements in the stream
  //terminal
  
  .collect() // collect all elements into a Collection takes a Collector object
  .collect(Collector.toList()) // convert stream to a List
  // terminal
  
  .reduce() // perform a cumulative operation
  // eg sum all elements
  // takes a instance of BinaryOperator Functional interface
  .reduce(0,(x,y)-> x+y) // 0+x+y
  //returns the result in the form of a Optional class object
  //Optional class is a wrapper class used to avoid null pointer exceptions
  //It mandates the use of methods which check for null values to retrieved boxed data
  // to get value use .get() or .orElse(defaultVal)
  // also has .isPresent() and ifPresent(Consumer)
  
  //terminal
  
  .max() // find max
  //terminal
  
  ```