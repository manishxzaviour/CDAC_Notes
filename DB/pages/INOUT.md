- both #out and #IN
- both read and write permission
	- pass by reference
	- address is passed #locator
-
- ```
  create procedure abc(inout y int)
  begin
  	set y=y*y*y;
  end;
  ```
-