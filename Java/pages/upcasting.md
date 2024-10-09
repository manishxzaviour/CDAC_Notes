- when the super class reference is used to represent the sub class objects
- used for #[[polymorphism/run_time]]
- so that sub classes created at runtime can be represented by the super class references
- for having simplified collection of different instances that share the same ancestors
- can also be used to access standard methods defined if the super class is abstract
-
- __grouping/representing the varying sub class objects simplify implementation__
- the sub classes may have hierarchical inherit the super class
-
- ```
  Person p = new Employee();	
  ```
- java supports #[[late binding]] by default
  there is no early binding
- ```
  p.accept()// Employee.accept()
  ```
-
- #[[object slicing]]
  the super class reference can only access the members visible to it
  all members of the sub class may not be visible through the super class reference