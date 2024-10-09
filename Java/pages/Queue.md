- interface that declares the __FIFO__ behavior
-
- is generally used as a __collection to store elements prior to processing__
-
- implemented by
	- #priorityQueue
	- #Deque
-
- > methods -
  |raise Exceptions|return special value|
  |add(e) {{cloze if allocated memory is full}} |offer(e) {{cloze return null if cannot be added}}|
  |remove(e) {{cloze if the element does not exist}}|poll() {{cloze return null}}|
  |get() {{cloze if empty}}| peek() {{cloze null if empty}}|
	- all methods implemented raise a exception on invalid conditions
	  these exceptions are handled in the internal implementations
-
- if a #Iterator is used a queue is traversed <u>from head to tail</u>
	- a iterator may fail to print in correct order if some order is maintained
-
- #Deque is a interface that extends the Queue interface