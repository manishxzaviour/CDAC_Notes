- ![Sunbeam_dac_rapid_fire_questions.pdf](../assets/Sunbeam_dac_rapid_fire_questions_1726415160499_0.pdf)
- Q1 
  logseq.order-list-type:: number
	- how does c++ manage its memory?
	  logseq.order-list-type:: number
	  > the cpp compiler organizes a applications memory
	  in three sections
	  >>data section {{cloze stores static and globally allocated entities and execution instructions. data about this is fixed at compile time. all entities are permanent}}
	  >>stack section {{cloze stores FAR and locally allocated entities memory allocated based on program execution entities are brought out and into stack based on program execution automatically}}
	  >>heap section {{cloze stores user allocated memory at run time allocation and deallocation of entities needs to be programmed by the programmer}}
	- explain new and delete operators for variables, objects and arrays
	  logseq.order-list-type:: number
	  >in cpp the new and delete operators are used to programmatically allocate and deallocate memory from the heap section
	  >> __for variables__ 
	  need to be pointers as the new operator returns the address to allocated memory. the identifier is passed to the delete operator to delete the memory through its pointer {{cloze dangling pointer and memory leakage}}
	  __for objects__ 
	  similar to variables the pointer to the object needs to be passed to delete and the constructor of the object to the new. when deallocating the destructor to the object is called
	  __for arrays__
	  the new operator can create the array just by using the array definition. the delete operator has overloaded [] operator that can be used to deallocate the array
- is it possible to delete memory acquired by a local variable in static memory using delete keyword in cpp?
  logseq.order-list-type:: number
  > a local variable allocated in static memory will be automatically deleted if it goes out of scope. the delete keyword cannot be used to delete this memory as the delete operator deletes the memory of a pointer that points to memory in dynamic memory allocated by the new operator
- Q3
  logseq.order-list-type:: number
	- what is the use of destructors?
	  logseq.order-list-type:: number
	  >  when the attributes of a class have dynamically allocated memory it is the responsibility of the class destructor to deallocate this memory when the class object goes out of scope. the destructor will call the delete operator to deallocate
	- write a legal example of destructor
	  logseq.order-list-type:: number
	  >~classname(){
	  delete abc;
	  }
- Q
  logseq.order-list-type:: number
	- what are the oop concepts present in cpp and java?
	  logseq.order-list-type:: number
	  > the cpp language supports all major pillars of oops:
	  >> abstraction - function call
	  >> encapsulation - function definition
	  >> modularity - header and source files
	  >> hierarchy - inheritance
	  __and minor pillars__
	  >> polymorphism - overloading
	  >> persistence - file io
	- explain with one example each
	  logseq.order-list-type:: number
- Q
  logseq.order-list-type:: number
	- how to create an abstract class
	  logseq.order-list-type:: number
	  >a class can be made as abstract if it contains atleast on pure virtual member function
	- how to write a pure virtual function
	  logseq.order-list-type:: number
	  > using syntax virtual function_name() = 0;
	- can we write a body of pure virtual function
	  logseq.order-list-type:: number
	  > a pure virtual function is ment to be overridden in all derived concrete classes. its body cannot be defined
- Q 
  logseq.order-list-type:: number
	- what is getter and setter?
	  logseq.order-list-type:: number
	  > are functions that allow to access read and write permissions to data members of the class. they are used to provide validation and abstraction.
	- why do we use that?
	  logseq.order-list-type:: number
	- write down a small example.
	  logseq.order-list-type:: number
- create a spiral matrix
  logseq.order-list-type:: number
- logseq.order-list-type:: number