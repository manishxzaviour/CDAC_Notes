- __display all the rows of sel1 and sel2__
- display null w.r.t the col when either is null
- i.e d.dname will be null if d.deptno is not found and e.ename will be null if e.deptno  is not found
-
- not supported in mysql
- ansi:
  ```
  select dname, ename from emp
  full outer join
  dept 
  on emp.deptno=dept.deptno
  ```
- mysql:
	- ```
	  select dname,ename from emp
	  left outer join
	  dept 
	  on emp.deptno=dept.deptno
	  union
	  select dname,ename from emp
	  right outer join
	  dept 
	  on dept.deptno=emp.deptno
	  ```
- oracle:
	- ```
	  select dname,ename from emp, dept
	  where dept.deptno(+)=emp.deptno
	  union
	  select dname,ename from emp, dept
	  where dept.deptno=emp.deptno(+)
	  ```
-
- ### parent-parent report, master-master report
-
-