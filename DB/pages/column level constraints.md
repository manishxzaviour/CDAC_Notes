- constrain a single column
-
- table level constraint : composite constraint
	- specified for two or more columns
-
- [[not null]]
	- nulls are not allowed for insertion {{cloze in mysql null can be assigned to all datatypes}}
	- ```
	  create table emp(
	  	empno int not null
	  );
	  ```
- [[check constraint]]
	- used for validations
	- ```
	  create table emp(
	  	emp int auto_increment primary key,
	  	ename varchar(25) check (ename=upper(ename)), -- is uppercase
	      sal float check (sal between 5001 and 99999),
	      deptno int foreign key
	      references dept(deptno)
	  );
	  ```
-
- allowed
	- #[[relational operators]]
	- #[[logical operators]]
	- arithmetic operators
	- #[[special operators]]