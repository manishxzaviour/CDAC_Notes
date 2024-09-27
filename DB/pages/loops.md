- - while
  ```
  while <condition> do
  :
  end while		
  ```
- __executed in server ram__
- - repeat loop
  like do while
  __no condition to enter but condition to leave__
  ```
  repeat 
  :
  until <condition>
  end repeat;
  ```
-
-
- operators
- - loop -> to assign a __identifier__ to the loop
	- used to jump from inner loop to some outer loops in nested loops
	- ```
	  pqr_lp:loop;
	  ```
- - leave -> to leave a running loop
	- like break
	- exit the loop
	- ```
	  leave pqr_lp;
	  ```
- - iterate -> skip the conde under it
	- like continue
	- ```
	  iterate pqr_lp;
	  ```
-
- #[[continue Handler]]