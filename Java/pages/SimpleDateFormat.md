- in java.text
- ```
  SimpleDateFormat sdf = new SimpleDateFormat("yyy-MM-dd");
  //Date d= sdf.parse("2024-10-1"); generates a checked exception
  try{
  	Date d= ...
  }
  catch(ParserException e){...}
  ```