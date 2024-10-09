- a built in handler that will execute a query statement if condition is met
- ```
  DECLARE handler_action HANDLER
  	FOR condition_value
      statement
  ```
- handler actions can be continue, exit, undo
- condition_value can be sql state, warning, exception NOT FOUND
-
- ```
  DECLARE DONE INT DEFAULT 0;
  DECLARE C1 CURSOR FOR SELECT * FROM TABLENAME;
  DECLARE CONTINUE HANDLER FOR NOT FOUNT SET DONE =1;
  OPEN C1;
  	LABEL: LOOP
      FETCH C1 INTO X,Y,..
      :
      IF DONE =1 THEN LEAVE LABEL;
      END IF;
      END LOOP;
  CLOSE C1;
  ```
-