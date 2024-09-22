- group by clause
	- create groups of rows based on one or more fields
-
- used when selecting group functions
- to select a single row function and a #[[group function]] together all single row functions present in select should be grouped using group by
-
- rows are searched, filtered and retrieved from HD to ram
  logseq.order-list-type:: number
- after retrieval the elements will be sorted because of grouping
  logseq.order-list-type:: number
- grouping is performed on the grouping field viz.
  logseq.order-list-type:: number
  separate array for each unique grouping field is created
-
- ```
  select deptno, sum(sal)
  from emp 
  group by deptno;
  ```
-
- - whichever column __is present in the select statement has to be present in group by clause__
- - whichever column __is present in the group by clause need not be be present in select statement__
-
- called #[[multi-dimensional queries]]
-
- ### [[having]]