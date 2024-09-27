- sequential storage of data of same type
- array is a #non-primitives
- there is a ~~class~~ array type for every data type
	- __JVM makes these classes at runtime__
- the object class is the super class
- #[[wrapper classes]]
-
- an array is essentially a object
-
- when an array of objects is created 
  the elements which are __references__ of data type of the array need to be initialized
- ```
  Student[] a=new Student[10]; //creates 10 references of the type students
  a[0]=new Student();
  ```
-
-
-
- ```
  int[] i = new int[5]; // i is a reference to a array of integer references
  int[] myNum = {10, 20, 30, 40}; // set value
  int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };
  
  ```
-
- 1D arrays
	- ```
	  int[] i =new int[5];	
	  ```
- 2D arrays / multi-dimensional arrays
	- ```
	  int[][] i = new int[2][3];
	  // each element is a reference of type int and needs to be initialized with a object
	  i[0][0] = new int(10);
	  // is a type of object 
	  //has fields and method
	  
	  int[][] b={{10,20},{30,40}};
	  ```
- ragged arrays
	- multi-dimensional array where not all rows are of equal lengths
	- ```
	  int[][] i = new int[2][];
	  i[0]=new int[2];
	  i[1]=new int[3];
	  //need to initialize all references
	  ```
-
- ### only during declaration can the new operator be skipped
	- is done implicitly
	- ```
	  int arr={2,3};
	  arr=new int[] {10,20,30,40};
	  ```