- similar to try in cpp
- additional
	- a try block must follow a catch block __or #finally block__
	- __try with resource__
		- ```
		  try(scanner sc=new Scanner(sysin)){...};
		  ```
		- will not need another #finally block as it will have a finally for the given resource
		- used only if the resource implements `AutoClosable`