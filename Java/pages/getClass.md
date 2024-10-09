- returns the runtime class of an object
- the class object is the object that is locked by static synchronized methods of the represented class
- #multi_threading
- is a #final method
-
- ```
  sysout(new Scanner(null).getClass())
  class java.util.Scanner;
  class x{
  @ override
  public booliean equals(Object obj){ 
  	:
  	if(getClass() != obj.getClass()) return false;
      :
  }
  ```
-
- #### getClass vs instanceof
- | tests weather the objects are identical | object reference LHS =RHS |
  |to match the class exactly instead of sub classes using == | else instanceof |
  |NullPointerException if object is null|return false if first operand is null|
-
-