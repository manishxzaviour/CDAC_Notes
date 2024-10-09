- a expression made using the lamda operator __->__
-
- ### short hand implementation of a function interface
-
-
- > (Params)->{operations; return val;}
- ```
  emp.sort(
  	new Comparator<Employee>(){
      	public int compare(Employee e1, Employee e2){...}
      }
  );
  
  emp.sort( // multilinear lamda expression
  (Employee e1, Employee e2)->{
  int diff = e1.roll-e2.roll;
  return diff;
  });
  
  emp.sort(
  (e1,e2)->{ // single line refered types
  return e1.roll-e2.roll;
  }
  );
  
  emp.forEach(
  (e)-> sysout(e);
  // implementation of Consumer<T> function;
  );
  
  emp.forEach(
  	new Consumer<Employee>{
      	public void accept(Employee t){
          	sysout(t);
          }
      }
  );
  
  test(BinaryOperation<Integer> op){
  	sysout(op.apply(10,20)); //
  }
  main->
  	test((x,y)->(x+y));
  ```
-
- lamda expression
	- anonymous class functionality;
	- anonymous class implements a functional interface;
	- provide implementation of the functional interface method;
-
-
- ### capturing lamda expression
	- lamda expression that uses a external variable for its expression
	- ```
	  main->
	  int z =30;
	  test((x,y,z)->x+y+z);
	  ```
	- z used as local scope variable inside the lamda function should be final or effectively final.
	- because of #nested_class
-