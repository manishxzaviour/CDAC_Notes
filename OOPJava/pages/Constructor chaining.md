- when one constructor of the class provides partial implementation or full implementation 
  it can be reused by calling from other constructors
- ```
  Class X{
  	int x,y;
  	X(int x, int y){
      	this.x=x;
          this.y=y;
      }
      X(){
      	this(0,0);
      }
  }
  ```
-
- the existing constructors are searched based on their signatures