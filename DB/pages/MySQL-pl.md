- programming language
- used for db programming
-
- for processing of data in db
	- server-side processing
-
- oracle - pl sql
  ms sql - t-sql
  mysql - mysql-pl
-
- ```
  delimiter :>
  begin
  :
  :
  end; :>
  delimiter ;	
  ```
-
- execution is top to bottom
-
- block level language
	- block within block
-
- inside a block DDL, DML, DQL, DTL/TCL allowed
	- dcl not allowed
-
- to store the output generally a temp table is created on per application bases
-
- programs are in the form of stored procedures {{cloze procedure is a routine that has to be called explicitly > call proc()}}
	- compiled forms stored
-
- #[[decision making]]
- #loops
-
- __global variables__
- ```
  set @x=10;
  ```
	- does not need a decleration
	- will exist in ram till exit
	- ```
	  select @x from dual;
	  ```
	- stores data in __character string__