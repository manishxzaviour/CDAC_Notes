- is a #handle to a table
	- contains a secondary mem pointer
	- stores the #locator to the table
- used to provide indirect access to the table data
	- for access control
- #[[column level security]] using select statement
- #[[row level security]] using where clause
-
- ```
  create view v1 
  as
  select empno, ename 
  from emp;
  ```
-
- a view to a table contains
	- a locator to the table for DML operators
	- the select query defining the access table in its compiled form
-
- a view is not a table just a handle to a table
- to grant DML permision
  ```
  grant insert, udate, delete 
  on 
  db.v1 to manish@host
  ```
  dml can be used only if constraints are met
  the view passes on the command query onto the table
- > insert update and delete access is granted by default
  to block access add to select with operator __with check option__
- a view can point to a alias table 
   but insert and update is not allowed
- ### usefull when there are many users who are assigned access to 
  certain rows and columns only and not the full table
-
- view is a #[[stored object]]
	- object containing the specified select is stored in the system table
- using view is __abstraction__ of the select statement
-
- views are executed are faster than regular select as they are stored in their compiled form
- if a table is dropped its view remains in the system table
	- the view needs to be dropped separately
- to change the select query of the view the view needs to be dropped or use 
  ```
  create or replace view v1 as select empno , ename from emp
  ```
-
-
- - to display the views
  >show tables - will show tables and views mixed together
  show full tables - will differentiate between table and views
  desc v1 - describe the view (accessible cols)
  show create view v1 - to see the definition of the view
- view based on view is allowed
	- to make union of more than 255 queries
	- to write subqueries with more than 255 levels
	- to have more than 255 nested functions
-
- > to simplify join of n number of selects.
    by splitting the join in multiple smaller joins
-