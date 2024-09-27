- display sel1 and sel2 selections
- if sel2 not found display null
- ```
  -- ansi
  select e.ename, d.dname 
  from emp e
  left outer join 
  dept d
  on e.deptno=d.deptno 
  
  --oracle
  select dname,ename from emp, dept
  where dept.deptno=emp.deptno(+)
  
  ```
- print e.ename and null if condition is false
- ## will print all rows of e
- e is #[[driven table]] #[[detail]] and d is #[[driving table]] #[[master]]
-
- # result is null on right side
-
- ___no of rows = no of rows on right side___