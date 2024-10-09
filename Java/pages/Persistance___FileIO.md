- IO in java 1.7 and NIO in java 1.8
- java.io and java.nio packages
-
- > IO framework is used for File io, Network io, Memory io and more
-
- File io is done using __IO streams__
- Streams determine the flow of data
-
- #IO_streams
	- ByteStreams
	- CharacterStreams
	-
	- Stream is abstraction of data source/ sink
		- InputStream, OutputStream ByteStream
		  Reader, Writer CharacterStream
		-
- All IO Streams are auto closable; #try with resource capable
-
- __Chaining IO streams__
	- #FileOutputStream -- write given bytes into the file on disk
		- can have append
		- ```
		  FileOutputStream fos = new FileOutputStream("name.txt"); // ("name.txt", true) // for append
		  ```
	- BufferedOutputStream --
	- #DataOutputStream -- convert given primitive into sequence of bytes
		- ```
		  FileOutputStream fos = new FileOutputStream("name.txt");
		  DataOutputStream dos = new DataOutputStream(fos);
		  dos.writeUTF(String)
		  dos.writeInt()
		  dos.writeDouble()
		  dos.writeShort()
		  ```
	- #PrintStream -- convert given input into formatted output
		- produce __formatted output__ (in bytes) and send to stream
		- >has print(), println(), printf()
		- is a parent class of the __System.out__ and __System.err__ objects
		- >PrintStream ps = new PrintStream("FILE_PATH");
		- Text written by the PrintStream can be read line by line using the `Scanner object`
	- #BufferedOutputStream -- to reduce frequent write operations that hamper performance
		- hold data into a in-memory buffer before writing
		- > Object -> ObjectOutputStream -> BufferedOutputSream -> FileOutputStream
		- data is written when buffer is full of is flushed
		- a buffer size can be provided at creation
	- #DataInput -- read form file
		- >readUTF()
		  int readInt()
		  double readDouble()
		  short readShort()
	-
-
-
- #Serialization
	- convert java object to/from bytes
	- > __object__ -> __ObjectOutputStream__ [writeObject()] -> __bytes__ -> __FileOutputStream__ -> __file__
	  __object__ <- __ObjectInputStream__ [readObject()] <- __bytes__ <- __FileInputStream__ <- __file__
	- Converting the state of the object into byte sequence is called serialization
	- Objects and their wrappers must be serializable to write them into the file
		- #### they must implement the <u>Serializable</u> marker interface
		- when writing a collection all its elements must be serializable
		- else throws `NotSerializableException`
-
- ```
  writeD(Employee e){
  	//FileOutputStream fs= new FileOutputStream("Employee.db",true);
      // trows checked exceptions IOException and FileNotFoundException
      try(FileOutputStream fs= new FileOutputStream("Employee.db",true)){ // autoclosable
      	try(ObjectOutputStream oos = new ObjectOutputStream()){
  			oos.writeObject(e);  
              // will not write transient or static fields
              // except the SerialVersionUID field
          }
      }
      //checked exceptions
      catch(IOException e){}
      catch(FileNotFoundException e){} // FileOutputStream
  }
  ```
-
- similar syntax for reading form the file
	- using ObjectInputStream, DataInputStream
	- the ois.readObject() returns the object in the Object class reference which needs to be downcasted
	- the readObject() throws the checked `ClassNotFound` Exception.
	- A file can be read in its entirety using a infinite loop. the InputStream will raise the 
	  `EOFException` if the pointer reaches the end.
	- the EOFexception is a unchecked exception
	- the programmer generally wants to handle it
-
- __transient fields__
	- #transient_fields
		- if a field is calculable at runtime, writing it to the file should be avoided as it will be redundant.
		- such fields can be marked using the `transient` keyword. will __not be written__ to the file.
		- when reading the object from the file the resultant object will have all transient fields initialized to null. {{cloze static fields are not stored but will have value at object creation as they are class level}}
		- they can be calculated later.
		-
- __SerialVersionUID__
	- #SerialVersionUID
		- each Serializable Class inherits a private static final long serialVersionUID field.
		- this field is initialized automatically to have a unique number to represent the class
		- if a class is modified its serialVersionUID changes automatically.
		- When a file containing object is read using the ObjectInputStream `.readObject()` it verifies the local class UID with the UID of object in class if they do not match it will throw the `InvalidClassException`
		- to avoid this a local field can be created which will mask the Streamable field.
-
- ### File_Class
	- #File_Class
		- used to access meta data of a __file__ or a __directory__
		- provides FileSystem APIs
	-
-
- #NIO
	- to provide a method of non-blocking while writing to a file
	- Normal IO write are blocking in nature
	- used channel and buffer to read and write
	- a channel points to the file location and the buffer is used to store data read from and written into the file
	- a buffer can be flush() and clear() to change write to read