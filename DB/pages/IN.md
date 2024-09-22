- __read only__
	- like `call by value`
- ```
  create procedure abc(in y int)
  begin
  	insert into tempp values(y);
  end;
  ```
-
- cannot assign value to the parameter
- __is default parameter type__
- ```
  set @x=10;
  call abc(@x);
  ```