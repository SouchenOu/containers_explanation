# containers_explination

Containers in C++ STL (Standard Template Library)
-------------------------------------------------

A container is a holder object that stores a collection of other objects (its elements). They are implemented as class templates, which allows great flexibility in the types supported as elements. 

The container manages the storage space for its elements and provides member functions to access them, either directly or through iterators (reference objects with similar properties to pointers). 

1:array: Static contiguous array (class template)

2:vector: Dynamic contiguous array (class template)

3:deque: Double-ended queue (class template)

4:forward_list: Singly-linked list (class template)

5:list: Doubly-linked list (class template)

6:Set: Collection of unique keys, sorted by keys  (class template)

7:Map: Collection of key-value pairs, sorted by keys, keys are unique (class template).

8:multiset: Collection of keys, sorted by keys (class template)

9:multimap: Collection of key-value pairs, sorted by keys (class template)


10:unordered_set: Collection of unique keys, hashed by keys. (class template)

11:unordered_map: Collection of key-value pairs, hashed by keys, keys are unique. (class template)

12:unordered_multiset: Collection of keys, hashed by keys (class template)

13:unordered_multimap: Collection of key-value pairs, hashed by keys (class template)

4:stack: Adapts a container to provide stack (LIFO data structure) (class template).

15:queue: Adapts a container to provide queue (FIFO data structure) (class template).

16:priority_queue: Adapts a container to provide priority queue (class template). 



std::allocator() in C++
-----------------------

A namespace is a declarative region that provides a scope to the identifiers (the names of types, functions, variables, etc) inside it. Namespaces are used to organize code into logical groups and to prevent name collisions that can occur especially when your code base includes multiple libraries. 
 
 
          namespace ContosoData
          {
              class ObjectManager
              {
                 public:
                    void DoSomething() {}
              };
              void Func(ObjectManager) {}
          }
          
          
          EXP:
          
           ContosoData::ObjectManager mgr;
           
           mgr.DoSomething();
           
           ContosoData::Func(mgr);
          
