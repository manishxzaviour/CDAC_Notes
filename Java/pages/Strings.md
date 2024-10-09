- Strings is a special class in java
- it is a __immutable__ representation of a sequence of characters
-
- setting value using #literals
	- >String s = "Manish";
	- when a string is initiated with a string type literal
	  the literal is stored in a special section of the Java heap called #[[Spring Pool]]
	- when another string is trying to be initialized with the same literal
	  another instance of the literal is not made {{cloze no data/text section like in cpp}}
	  instead the previously stored literals ref is passed; from within the #[[Spring Pool]]
	- >String s2="Manish";
	- ```
	  s==s2
	  //>will return true as both the refernces
	  //s and s2 point to the same location inside the string pool
	  ```
- ```
  String s1="BatMan";
  String s2="Man";
  String s3 = "Bat"+"Man";
  s3==s1 && s3.equals(s1) //> true
  // literal operations like concat are performed at compile time 
  // s3= "BatMan" // at runtime
  
  String s1 ="Hello";
  String s2 = s1;
  s2="Me"; // will not change s1 // will create a new ref for Me in the string pool
  // Strings are immutable
  
  String s1= new String("Manish");
  String s2= new String("Manish");
  // will create two different objects inside heap and not inside the string pool
  s1==s2 //> returns false
  s1.equals(s2) //> returns true
  ```
-
- the String class is a `final` class and all its methods are final
	- the string class has the equals method overriden
-
- all run time operations create new objects in heap