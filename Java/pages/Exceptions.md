-
- #Throwable
	- #Exceptions - logical errors that are caused by external components; can be handled programmatically
	- #Errors - problems that occur in RENV; are not meant to be handled
-
- Java has many prebuilt exception classes
	- all exception classes are sub classes of the `Exception` super class #[[Exception class]]
-
- Exceptions are categorized as checked and unchecked
	- `checked` - exceptions that are __not compulsory to handle__
		- may have internal catch to handle in the hierarchy
		- All sub-classes of the Exception classes except the RunTimeException and its sub classes
	- `unchecked` - exceptions that __require handling__ compulsorily
		- all RunTimeException and its sub classes
-
- when a section can raises multiple possible exceptions
	- the method itself can only throw one Excetion
	- to throw multiple without using the generic super class of Exception
	- a Exception can be chained inside other
	- the wrapper exception will be declared as throws
	- ```
	  void task() throws SQLExcetion{
	  	if(connection==null)
	      	throw new SQLException(new NullValueException()); 
	          // the exception must supply a constructor that allows chaining
	          // SQLExcetion(Throwable cause); SQLException(String msg, Throwable cause);
	  }
	  ```
-
- #[[custom exception]]
	- a user defined exception is a class that is the type of Throwable class
	- for creating __checked__ exception
		- inherit from the `Exception` class
	- for creating __unchecked__ exception
		- inherit from the `RunTimeException` class
	- ```
	  public class InvalidLengthException extends RunTimeException{
	  	//unchecked
	      private static String msg;
	      public InvLExp(){
	      	//contr
	      }
	      public InvLExp(String msg){
	      	super(msg);
	      }
	      @override
	      public void printStackTrace(){
	      	sysout(msg); // allows user defined display message
	          	// if not overriden the super class method will be called
	      }
	  }
	  
	  main{
	  	:
	      try{.. throw InvalidLengthException();// throw InvalidLengthException("Message");}
	      catch(InvalidLengthException e){e.printStackTrace();}
	  }
	  ```