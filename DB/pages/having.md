- #[[having clause]]
- __cannot be used without a group by clause__
- used to specify conditions on aggregate values or groued columns
-
- ```
  select deptno, sum(sal) from em
  group by deptno
  having sum(sal)>9000
  ```
-
- the #where clause is executed for each record while the having clause is executed for each group
-
- using having reduces performance as compared to where clause