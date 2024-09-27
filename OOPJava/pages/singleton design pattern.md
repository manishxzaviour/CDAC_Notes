- to create only one instance of the class and make it accessible through a global point
-
- ```
  class Singleton{
  	private static Singleton instance = null;
  	private Singleton{
      	...
      }
      public Singleton getInstance(){
      	if(this.instance==null) this.instance = new Singleton();
          return this.instance;
      }
  }
  ```