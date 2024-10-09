- used to __Route__ the exception upstream for the calling function to handle
	- handled where the method is invoked
- ```
  class Time{
  	:
      public setMins(...) throws Exception{
      	:
          if(condition) throw new Exception(); // checked exception
      } 
  }
  
  class ...{
  	main(){
      	Time t=new Time();
          //t.setMin(...); will cause error as the method throws a checked exception that needs to be handled
          try{
          	t.setMin(...);
          }
          catch(Exception e){
          	e.printStackTrace();
          }
      }
  }
  
  ```
- ~~main can have throw but it is highly unrecomended.~~
	- ~~it will route the exception to JVM env which will crash the program~~
-
-