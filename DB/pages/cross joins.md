- join in two different tables
- join without any conditions #[[Cartesian join]]
- output rows = rows1 * rows2
- like a cross product
- ### for each column of table1, all rows of table2 are scanned
- ```
  select e.enam,d.dname from emp e
  cross joint dept d;
  ```
-
- for each emp e
	- for each dept e
		- print e, d
-
- will have duplicates and reverse duplicates
-
- ## all possible combination of rows
-
- ___no of rows = left rows * right rows___