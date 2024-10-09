- provide the reference of a existing method instead of defining own implementation
-
- ```
  test((x,y)->x+y);
  test(Integer::sum); //of util.function
  
  emp.forEach(
  	(e)->sysout(e);
  )
  emp.forEach(
  	System.out::println //:: is method reference operator used to acess static member function
  )
  ```