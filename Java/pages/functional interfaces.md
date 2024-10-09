### interface with only one abstract method
-
- ```
  @FunctionalInterface
  interface Acceptable{
  	void accept();
  }
  ```
-
- there can be only one abstract method with other default method or static method
	- e.g. Comparable(compareTo)
- #@FunctionalInterface is used to perform compile time check
-
- the `java.util.function` contains useful generic functional interface
	- >Predicate<T>: test: T -> boolean
	  Function<T,R> apply: T -> R
	  BiFunction<T,U,R> apply: (T,U) - > R
	  UnaryOperation<T> apply: apply : T -> T
	  BinaryOperator<T> apply: (T,T) -> T
	  Consumer<T> accept: T -> void
	  Supplier<T> get: () -> T
-
- #lamda_functions are used to implement functional interface
	- foundation for #method_references
	-
-
- ```
  List<Employee> emp = new ArrayList<>();
  Comparator<Employee> comp = new EmpidComparator();
  emp.sort(comp);
  
  
  ```