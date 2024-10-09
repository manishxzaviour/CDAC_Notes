- a class in java.util
	- ```
	  Date d1= new Date();
	  ```
	- prints `weekday month date HH:MM:SS timezone year`
	- new Date(2024,10,1);
		- prints wrong date as internally `Date(2024-1900,10-1,1);`
	- individual date, month and year __cannot be accessed__ depricated
	-