- #[[column level constraints]]
-
- similar to #pk no duplicates allowed
	- __nulls are allowed__
-
- text and blobs cannot be unique
-
- unique index is automatically created
-
- composite unique keys can be created
-
- multiple unique keys can be created
	- multiple candidate keys can be created by having unique with not null keys
-
- ```
  create table emp(
  	mob_no char(10) unique,
      unique(deptno, empno)
  );
  
  alter table emp add constraint u_emp_mob_no unique(mob_no);
  
  ```