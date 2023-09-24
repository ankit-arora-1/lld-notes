# Collections Framework
---

## Overview
---
A collection is an object that represents a set of Objects (example: ArrayList). Collections framework represents a group of interfaces and classes to work easily with collections. 
Below is a rough hierachy for collections framework (There is no need to remember this): 
<Add collections diagram here>

Advantages of collection: 
- Consistent API: The API has a basic set of interfaces like Collection, Set, List, or Map, all the classes (ArrayList, LinkedList, Vector, etc) that implement these interfaces have some common set of methods.
- Reduces programming effort: A programmer doesn’t have to worry about the design of the Collection but rather he can focus on its best use in his program. Therefore, the basic concept of Object-oriented programming (i.e.) abstraction has been successfully implemented.

## ArrayList
---
- Dynamic in nature, i.e., there size can be increased.
- Uses Arrays internally.
- If this array gets filled up, a new bigger array is created and the elements from previous array is copied to this. Hence, "put" time complexity for ArrayList is amortized O(1).
- They are not thread safe.

## Vector
---
- They are like ArrayList but they are thread safe.
- They are more common in legacy applications.
- They have synchrionized methods so they are thread safe.

## HashMap
---
- Uses buckets (arrays) internally to store data.
- The position at which an element is put is decided by the hash method. This hash method uses the hashcode of the object (which can be overriden by us) and another hash method (for better distrubution of data. Cannot be overriden by us)
- Once the hashmap fills map fills up to a certain degree, a new length buckets are created and rehashing of all the elements are done.
  - This is done based on a concept called a load factor. Load factor is a measure of how full the buckets are supposed to get before rehashing is done.
  - When number of enteries gets greater than load factor * capacity, rehashing is done. This is around .75 by default (Can be modified)
- HashMaps are not thread safe

Note: Collections framework contains a lot of other collections like Set, Queue, etc. Please read about them from the official documentation. 

# Iterables and Iterators
---
- Iterables respresents a data structure that can be iterated over.
- Iterable interface provides a method that produces an "Iterator"
- Iterator interface contains "hasNext" and "next" method where the logic for the iteration goes.
- Enhanced for loops make use of iterators interally. (Check this [example](https://github.com/ankit-arora-1/java-examples/tree/main/src/iterableanditerator))
- The reason we have Iterable and iterators is because each iterator is supposed to be independent of each other. So every time an iterator is called, it should not have any relation with the old one.
  
# Comparable and Comparator
---
- Comparable are used to define a natural order (default order) for a class. This is useful wherever some kind of comparison needs to happen between objects.
  - For example: We can't pass a custom object to a PriorityQueue in java if they do not implement Comparable because PriorityQueue needs a way to do some comparison between objects
- Comparable interface exposes "compareTo" which returns an int.
  - If the return value is +ve: this > other
  - If the return value is -ve: this < other
  - If the return value is 0: this == other
- Refer to this [example](https://github.com/ankit-arora-1/java-examples/tree/main/src/comparableandcomparator)https://github.com/ankit-arora-1/java-examples/tree/main/src/comparableandcomparator.

