- if - else if - else statement
-
- if <condition> then statement;
- elseif in oracle
-
- case statement
	- ```
	  delimiter :>
	  create procedure abc()
	  begin
	  	case
	      when x>5000 then <s1>
	     	when x=2000 then <s2>
	      :
	      else <sn> -- not cumpulsory officialy but empty else block required 
	            -- if none of the case selected then error if no else
	      end case;
	  end; :>
	  delimiter ;
	  ```
-