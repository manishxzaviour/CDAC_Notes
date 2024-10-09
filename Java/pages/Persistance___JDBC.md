### to use a RDBMS for data storage
- RDBMS sevices understand SQL only
- a JDBC driver converts java request to database understandable form
	- convert database response in java understandable form
-
- #JDBC_Drivers
	- types of JDBC drivers
		- #JDBC_ODBC Bridge
		  logseq.order-list-type:: number
			- standard for connecting to RDBMS; provided by Microsoft
			  logseq.order-list-type:: number
			- can be used to easily connect to any database
			  logseq.order-list-type:: number
			- slower execution as has to be passed through multiple layers
			  logseq.order-list-type:: number
		- #Partial_Java|Native_driver
		  logseq.order-list-type:: number
			- partially implemented in java and other in cpp via JNI
			  logseq.order-list-type:: number
			- different driver for different RDBMS
			  logseq.order-list-type:: number
			- faster execution time
			  logseq.order-list-type:: number
			- not truly portable
			  logseq.order-list-type:: number
		- #Network_driver
		  logseq.order-list-type:: number
			- a network machine that transfers translated requests and responses over the network
			  logseq.order-list-type:: number
		- #Database_specific driver (Type-4)
		  logseq.order-list-type:: number
			- most widely used
			  logseq.order-list-type:: number
			- database specific driver written completely in java 
			  logseq.order-list-type:: number
			- provided by RDBMS maintainers
			  logseq.order-list-type:: number
			- fully portable
			  logseq.order-list-type:: number
-
- ### MySQL connector
	- #MySQL_connector
		- mysql JDBC driver
		- com.mysql.cj.jdbc.Driver // for connection ; cj stands for written in core java
		- A driver needs to be registered with the DriverManager before use
		- done automatically when the DriverManager.getConnection() is called
		- to configure manually Class.load("fully qualified class name")
		-
		- create connection
		  logseq.order-list-type:: number
			- logseq.order-list-type:: number
			  ```
			  Connection connection = DriverManager.getConnection(URL,USERNAME,PWD);
			  ```
			- logseq.order-list-type:: number
			  > URL - "jdbc:mysql://host:3306/dbname"
		- create statement
		  logseq.order-list-type:: number
			- logseq.order-list-type:: number
			  ```
			  Statement stment = connection.createStatement()
			  stment.execute(sql); //sql is a sql query in string format
			  // returns true if a ResultSet object is returned
			  
			  //if user input is concatinated with this sql string 
			  // there is scope for sql-injection attack
			  // the queries written to accept user data have low readability
			  // should not be used for parameterized queries
			  ```
			- logseq.order-list-type:: number
			  ```
			  String sql = "
			  	Select * from emp where empid = ?
			  "
			  PreparedStatement ps = connection.preparedStatement(sql);
			  // compulsory to provide a sql query
			  // the user parameters can be inserted into the query using the ? placehoder
			  // the values are entered later
			  
			  ps.setInt(1,id); // first occurance of ? in the query is replaced with id 
			  ps.executeQuery();
			  ```
			- if a query returns results in form of table; it can be accessed using the `ResultSet` object
			  logseq.order-list-type:: number
			  ```
			  ResultSet rs = ps.executeQuery(); //stment.executeQuery(sql)
			  								 //ResultSet rs = stment.getResultSet();
			  while(rs.next()){ // increments record pointer ; initially -1
			  	rs.getInt(1); // read int from column 1
			  }
			  ```
		- logseq.order-list-type:: number