- raise a exception that will need to be handled
- a Exception will be a anonymous class
- used to throw a user defined or framework exception
- ```
  class Time{
  	setHrs(...){
      	try{
      	if(condition)
          	throws new RunTimeException(message); // unchecked exception
              //Exception class would be a checked exception
      	}
          catch(RunTimeException e){
          	...
          }
      }
  }
  ```
-
- A #checked_exception requires compulsory handling
	- by design exception handelling is to be seperated from the logical part of the execution
		- i.e outside of the method call; in the calling code
	- so to mitigate this the #throws keyword is used to __route__ the exception __upstream__
	-