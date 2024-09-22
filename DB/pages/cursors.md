- a variable that can store multiple rows and columns
- to solve problem of repeated i/o to do operations of fields of one table
-
- store and process multiple rows and cols __temporarily__ and is __read only__
- a cursor is similar to a 2d array
- ```
  declare pqr cursor for select * from emp;
  ```
- can be formed on join
- ```
  delimiter //
  create procedure abc()
  begin
  	declare a int;
      declare b varchar(15);
      declare c int;
      declare d int;
      declare x int default 0;
      declare
   c1 cursor for select * from emp;
      declare continue handler 
      not found set x=1;
      open cl;
      	c1_loop:loop;
          fetch c1 into a,b,c,d;
          if y=1 then 
          leave c1_loop;
          end if;
          insert into tempp values(a,b);
          iterate c1_loop;
          end loop;
      close c1;
  end; //
  delimiter ;
  ```
-
- a #cursor i supposed to be declared after all the variables
- when open cursor is executed the select query of the cursor is executed
	- the cursor pointer will point to the first row
- after #fetch ing the first row the cursor pointer points to the second row automatically
- on cursor close, the cursor memory will be deleted from the ram
-
- if the #fetch condition is iterated for more than the size of selected rows the row id will point to null and will set the `not found` flag.
- the `continue handler` is a default exception of the cursor.
-
- the #fetch command will copy data from one row of the cursor into intermediate variables of the same type.
	- cannot fetch multiple rows at a time or sequentially
-
- a #cursor can have a select query that has a order by clause
	- e.g can get first/last 10 rows
	- is called "cursor fetching"
-
- after a update occurs the cursor will still hold copy of previous data
	- to avoid this rows should be locked manually
	- ```
	  select * from emp for updates; -- will display all the rows
	  
	  create procedure abc()
	  begin
	  	declare cursor c1 select * from emp for update; 
	      -- will just copy tables into c1 insted of printing
	      open c1; 
	      close c1;
	  end;
	  call abc();
	  ```