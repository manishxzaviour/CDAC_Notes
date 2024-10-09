- #anonymous_object
- ```
  class ComparatorName implements Comparator<Employee>{
  ...
  }
  Comparator<Employee> comp = new ComparatorName() 
  
  Comparator<Employee> comp = new Comparator<Employee>(){
  //(){} - anonymous class implementation that implements Comparator
  // object is not anonymous
  	public int compare(...){
      	return ...
      }
  }
  emp.sort(comp);
  
  emp.sort(
  	new Comparator<Employee>(){
      	public int compare(...){
      		return ...
      	}
      }
  ); // anonymous object of a anonymous class
  
  ```