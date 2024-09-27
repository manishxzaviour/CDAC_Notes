## select __matching rows__
- ```
  select e.ename, d.dname 
  from emp e
  inner join dept d
  on e.deptno=d.deptno; --condition for matching
  ```
-
- can also be made using where clause
- most common type of join hence #[[natural join]]
- also called as #equijoin
-
- there exists #inequijoin where the non matching of the two tables are selected
-
-
- all the joins are inner joins but with their own conditions