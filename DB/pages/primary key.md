- #PK
- key where
	- > duplicates are not allowed
	  null values are not allowed
-
- used for uniqueness of records for search
- every table must have one primary key and only one primary key for a table
-
- a primary key can be made by combining two or more columns together <u>composite primary key</u>
	- in mysql upto 32 cols can be combined
-
- > #rowid is not a primary key as it is a pseudo column containing the physical address
  rowid is not constant so it is not a good primary key
-
- Text and blob cannot be primary keys {{cloze too big}}
-
- a unique #index is created automatically
	- THE PK is the best candidate to form a index
- if a composite primary key is created, a composite unique key is created automatically
-
- ### steps to identify a primary key
- identify a candidate key and make it the primary key
  logseq.order-list-type:: number
	- else implement composite primary key
	  logseq.order-list-type:: number
- if not add a #[[surrogate key]]
  logseq.order-list-type:: number
- ```
  - alter table emp drop primary key; -- only remove the constraint
    alter table emp add primary key(empno); -- adds after table defination  
    
    --define composite primary keys at the end of table structure  
    
    create table emp(  
    	empno char(4),  
        ename varchar(15),  
        sal float,  
        deptno int,  
        primary key(deptno, empno) --order of pk defination matters for performance 
        			--(parent, child) 
    );
    
  ```