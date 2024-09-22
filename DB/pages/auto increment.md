- ```
  create table ab(
  y int auto_increment;
  );
  ```
- ## rollback and commit have no effect on auto_increment
- once incremented cannot be set back
	- by design to provide stability with multi-users