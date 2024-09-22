- when parent column and  child  column are present in the same table
-
- using #alias join a table to itself
	- the whole column is not transferred to the ram twice only the requested columns
-
- based on recursion and is the slowest type of join
-
- ```
  select a.ename, b.ename
  from emp a, emp b
  where a.mgr=b.emp;
  ```
-