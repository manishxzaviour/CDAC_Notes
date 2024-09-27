- used to initialize the static data members
- ### executed when the class is loaded
- executed only once
-
- ```
  Class x{
  	public static int x;
      static{
      	x=10;
      }
  }
  ```