- ```
  StringTokenizer st=new StringTokenizer("Manish Patil");
  while(st.hasMoreTokens())
  	string token=st.nextToken();
  //> 
  	Manish
      Patil
  StringTokenizer st=new StringTokenizer("www.manish.patil/accept","./"); // delimiter . or /
  //>
  	www
      manish
      patil
      accept
  
  ```