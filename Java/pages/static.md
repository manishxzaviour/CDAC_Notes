- __modifier__
- a member common to all instances
- may be a __data member or member methods__
-
- > if multiple instances of a class require the same resource, then the resource should be made static so that it can be shared across all objects
-
- The memory for a static #field is __allocated only once__
  in the method area at the time of class loading
-
- static methods do not get a this reference as they are designed to be on class level
  and called using the class identifier {{cloze scope specifier :: in cpp}}
- ```
  Class x{
  	static int x=10;
      static int p(){..};
  }
  :
  x.p();
  x.x=20;
  ```
-
- ### can be initialized using
	- #[[field initializer]]
	- #[[static initializer]]
-
- ```
  class BankAccount{
  	private final int accountNo=++gen_accno;
      :
      private static int gen_accno; // can be initialized here directly // field initializer
      :
      {
          accountNo=++gen_accno; 
          // will be executed for each created object
      }
      :
      static {
      	gen_accno=1000; // executed only once
      }
  
  }
  ```
-