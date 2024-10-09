- enums are enumirated types
- used to represent any primitive or non-primitive using a string literal {{cloze used to provide string identifiers for integer constants in cpp}}
-
- ```
  enum Choice{
  	EXIT, ADD, SUBTRACT
  }
  
  case Choice.Exit break;
  
  int i = Choice.ADD; // not possible in java
  ```
-
- __Enum is a abstract class in Java.__
	- when compiled the enum structure will be converted to a final class
	- after compilation each enum is stroed in its own class fine
-
- ```
  enum Choices {
  	EXIT, ADD, SUB;
  }
  converted during compilation=>
  
  final class Choices extends Enum<Choices>{
  	public static final Choices EXIT;
      public static final Choices ADD;
      :
      static{
      	EXIT = new Choices("EXIT",0);
          :
      }
      private Choices(String name, int ordinate);
      public static final choices[] values();
      public static final Choices valueOf(String s);
  }
  
  main =>
  	Choices[] arr = Choices.values();
      for
      	sysout(c.ordinate());
          
  enum AccountType{
  	private double roi;
      SAV(3.5), CUR(1.5), DMAT(0);
      private AccountType(double roi) { 
      // converted to (String name, int ordinate, double roi)
       	this.roi = roi;
      }
      
  enum AccountType{
  	private double roi;
      SAV(3.5){ // creates an anonymous class
      	String toString(){
          	return "SAVINGS";
          };
      }, 
      CUR(1.5){ // each anonymous class will have its own file
      	String toString(){
          	return "CURRENT";
          };
      },
      DMAT(0);
      
      private AccountType(double roi) { 
       	this.roi = roi;
      }
      
      main =>
      	sysout(AccountType.SAV);
      
  ```
-
-
- can created #anonymous_class to provide specific behaviours
-
- As enums are converted into classes they can be directly implemented using used defined class.
  this will allow greater flexibility.
-