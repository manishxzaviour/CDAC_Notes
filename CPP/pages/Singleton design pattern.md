- when only one object is to be created on the global scope
	- ```
	  class X{
	  	public X(){
	      	..
	      }
	  } // can create multiple instances of the object as the constructor is available publicly
	  
	  class Singleton{
	      private static Singleton* instance;
	  	private Singleton(){
	         ..
	       this.instance=null; // early initialization 
	      }
	     public Singleton* getInstance(){
	  		if(instance==null)
	          	this.instance*=new Singleton(); // late initialization 
	             return this.instance;
	      }
	  }
	  // only one object will be created and returned
	  // when invoked again the same address will be returned;
	  
	  ```
-
- ### it ensures  a class only has one instance, and provides a global point to access it
-
- __Singleton classes are used for logging, driver objects, caching, and thread pool, database connections.__
-