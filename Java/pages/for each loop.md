- ```
  for(elementType ele : collection){
  	//ele is a local copy of element inside of collection
  }
  ```
-
- ```
  Students[] s = new Students[5];
  //initialize all references
  for(Student e : Students){
  	e.display();
      e.accept();
  }
  ```
-
- the for each loop __cannot initialize__ the elements of a collection but can __only manipulate__ them through reference address.
-
- usually used for manipulation and iteration of existing elements