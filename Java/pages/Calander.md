- IS  a abstract class; used to convert a given instance into calander fields
	- YEAR, MONTH, DAY_OF_MONTH, HOUR ..
- Calander is #[[locale sensitive]] class and provides a `getInstance` to acess its instance
	- `factory pattern`
	- returns a Calander object whose fields are initialized with the current date and time
	- >sysout(c.get(Calender.MONTH));4
	  sysout(c.get(Calander.YEAR));
- Fields in a calender are __MUTABLE__