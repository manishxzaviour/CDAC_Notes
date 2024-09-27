- when previous upcasting is performed; 
  #[[object slicing]] takes place
- to access the members not visible through the super class reference downcasting needs to be performed
- in java explicit casting is the only way of down casting
- ```
  Person p = new Employee();
  Employee e = (Employee) p;
  ```
-
- will raise the `ClassCastException` if the class are not inherited
-