- is a #[[thread safe]] __Mutable__ sequence of characters
- ```
  StringBuffer sb1=new StringBuffer("Manish");
  StringBuffer sb2=new StringBuffer("Manish");
  
  (sb1==sb2)  //> false
  sb1.equals(sb2) //>false
  ```
- the #StringBuffer and #StringBuilder are `not final` and do not override the equals method
	- to check equality - convert to string and use equals
-