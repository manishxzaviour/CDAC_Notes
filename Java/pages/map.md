- public interface Map<K,V>
-
- Implemented by
	- HashMap {{cloze no particular order - override hashCode and equals}}
	- LinkedHashedMap {{cloze insertion order preserved}}
	- TreeMap {{cloze sorted order of keys}}
	- __HashMap and LinkedHashMap allow null__ key value. 
	  only one key value is inserted
	  ___Null is not allowed in TreeMap___
-
- if Keys are same at insertion values are replaced
-
- > methods-
  clear()
  compute()
  computeIfPresent()
  containsKey()
  containsValue()
  equals()
  get(k)
  getOrDefault(K,V)
  merge(e)
  put(K,V)
  remove(K)
  replace(K,V)
  size()
  values()
- > Map<Integer,String> StudentMap = new HashMap<>();
  StudentsMap.put(10,"Ramesh")
-
- A Map does not have a iterator
	- to iterate a map is converted to a key set using the keySet method
	- >Set<Integer> keys = StudentMap.keySet()
	- the values can be retrieved using the values() method; else the get method can be used
	- >Collection<String> e = StudentMap.values()
	- to get a entire K,V pair __entrySet()__ method can be used; returns a set
	- the elements of a set are of the __Map.entry__ type // is a __interface__
	- ```
	  Set<Map.Entry<Integer,String>> ent 
	  = StudentMap.entrySet();
	  ```
	- Entry is a nested interface within the Map interface
	  > Methods of the Map.Entry interface
	  getValue()
	  getKey()
	- ```
	  for(Map.Entry<Integer,String> ele : ent)
	  sysout(ele.getKey());
	  sysout(ele.getValue());
	  ```
	- the map can be printed using its toString() method
-
- a #set can be considered as a Map with Keys but all values are null
-