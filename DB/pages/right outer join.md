- display sel1 and sel2 selections
- if sel1 not found display null
- ```
  --ansi
  select e.ename, d.dname 
  from emp e
  right outer join 
  dept d
  on e.deptno=d.deptno 
  
  --oracle
  select dname,ename from emp,dept
  where /*outer table*/ 
  		 dept.deptno(+)=emp.deptno 
          				  --inner table
  ```
- print null and d.name if condition is false
- ### will print all rows of d
- d is #[[driven table]] #detail and e is #[[driving table]]
-
- ## display null on the left side
-
- no of rows = no of rows in right table
-