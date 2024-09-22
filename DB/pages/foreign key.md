- <https://en.wikipedia.org/wiki/Foreign_key>
	- a set of #attributes in a #table that refers to the #[[primary key]] of another tabl
	- reference a #[[candidate key]]
- table containing the foreign key is called the #[[child table]]
- table containing the reference/ candidate key is called #[[parent table]]
-
- in general a foreign key equals to the candidate key in some row of the primary table
-
- a foreign key may also reference column of the same table
	- also known as `self referencing`
- a foreign key may contain duplicates  and nulls unless specified otherwise
-
- ```
  create table emp(
  	empno char(4) primary key,
      ename varchar(25),
      sal float,
      deptno int,
      mgr char(4),
      constrasint fk_emp_deptno foreign key(deptno) 
      references dept(deptno)
      on delete cascade 
      -- to maintain db integrity 
      -- delete if parent key is deleted
      -- to preserve child nodes set child rows to null
  );
  ```
-
- a parent col cannot be updated if child node exist already
	- make child node null then update parent
	-