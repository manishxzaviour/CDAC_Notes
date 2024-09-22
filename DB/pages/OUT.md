- __write only__
	- like pass by reference
- can pass variables only
	- cannot pass literals and expressions
- ```
  create procedure abc(out y int)
  begin
  	set y=100;
  end;
  ```
-
- __address of the variable__ #locator is passed with read restriction
-