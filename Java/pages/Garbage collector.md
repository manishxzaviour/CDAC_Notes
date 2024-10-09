- A JVM mechanism for __preventing memory leakage__ and __automatic memory management__
-
- works on the Heap memory
- divided as
	- young generation
	- old generation
	- permanent gen
-
- a object will be marked for collection if
	- reference to the object from outside the heap becomes null
	- when the reference is overwritten
	- when the reference is lost
-
- the GC is invoked at certain defined intervals
-
- the GC functionality can be divided into
	- minor and major GC
-
- __Minor GC__
	- only works on the young generations
	- checks if all the objects present have a external reference
	- objects who have missing ref are marked for removal
	- uses the `Mark and compact` algo to mark the objects
	- > Objects that have been checked more than set threshold of minor GC runs
	  are moved into the `old gen`
- After some threashold of minor gc runs
  Major GC will be executed on both young and old generations
-
- > the #[[object class]] finalize() method {{cloze used to release resources captured in object fields }} of the object before destroying the object. the finallize method is to be overridden in the instances class
  ~~the finallize method is deprecated in java 1.9~~