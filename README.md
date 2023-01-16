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
          
std::allocator() in C++ :
-----------------------

Allocators are objects responsible for encapsulating memory management. std::allocator is used when you want to separate allocation and do construction in two steps. It is also used when separate destruction and deallocation is done in two steps. All the STL containers in C++ have a type parameter Allocator that is by default std::allocator. The default allocator simply uses the operators new and delete to obtain and release memory. 

Member functions associated with std::allocator() :

1:address: It is used for obtaining the address of an object although it is removed in C++20.

2:construct: It is used to construct an object.It is also removed in C++20.

3:destroy: It is used to destruct an object in allocated storage.It is also removed in C++20.

4:max_size: It returns the largest supported allocation size.It is deprecated in C++17 and removed in C++20.

5:allocate: Used for allocation of memory.

6:deallocate: Used for deallocation of memory.


As we know all the STL containers in C++ have an Allocator as a type parameter which is std::allocator by default. Underlying, it uses the new and delete operators to allocate and deallocate memory.

By definition, allocators are objects responsible for encapsulating memory management. It is useful when we want to separate memory allocation and object construction in two steps and separate deallocation and object destruction in two steps as well.

So what does this mean? For example, consider the following code:

                    int* vPtr = new int[3];
                    
With new operator, it forces us to allocate and construct all objects, 3 integer values, at the same time. Let’s say we only want to allocate (or preserve) 3 integer size memory areas and construct these integer values later, for instance we only want to construct the first integer value. std::allocator can help us to do that.

Allocators

The allocator is responsible for managing raw memory storage and also for constructing and destroying allocated objects in two seperated steps. Its declaration is:

template <class T> class allocator;
 
The most advantage of using allocator is:

Allocator allow us to have control over which constructors are called so the allocation and constructor are seperated.
 
 
                   #include <memory>
                   #include <iostream>
                   #include <string>
 
                  int main()
                  {
                     std::allocator<int> intAlloc;
                     // Allocate memory area for 100 integers
                     int* intArray = intAlloc.allocate(100);
                     // Construct the 5th element
                     intArray[4] = 2011;
                     std::cout << "intArray[4]: " << intArray[4] << std::endl;
                     // Deallocate the memory area
                     intAlloc.deallocate(intArray, 100);
                  }
1: Vectors:
 ----------
 
 In this tutorial, we will learn about vectors in C++ with the help of examples.

In C++, vectors are used to store elements of similar data types. However, unlike arrays, the size of a vector can grow dynamically.

That is, we can change the size of the vector during the execution of a program as per our requirements.

Vectors are part of the C++ Standard Template Library. To use vectors, we need to include the vector header file in our program.
 
 
         #include <vector>
 
1-1:  -C++ Vector Initialization
 --------------------------------
 
Method 1:

           vector<int> vector1 = {1, 2, 3, 4, 5};
 
 Method 2 :
 
           vector<int> vector3(5, 12);
 
           This one equivalent to 
 
           vector<int> vector3 = {12, 12, 12, 12, 12};

 
 
 
 
 
 code example:
 
 
                      #include <iostream>
                      #include <vector>
                      using namespace std;

                      int main() 
                      {

                                // initializer list
                                   vector<int> vector1 = {1, 2, 3, 4, 5};

                               // uniform initialization
                                  vector<int> vector2{6, 7, 8, 9, 10};

                              // method 3
                                 vector<int> vector3(5, 12);

                                 cout << "vector1 = ";

                            // ranged loop
                                 for (const int& i : vector1) 
                                 {
                                     cout << i << "  ";
                                 }

                                cout << "\nvector2 = ";

                          // ranged loop
                                for (const int& i : vector2) 
                                {
                                    cout << i << "  ";
                                }

                                cout << "\nvector3 = ";

                         // ranged loop
                               for (int i : vector3) 
                               {
                                   cout << i << "  ";
                               }

                                  return 0;
                       }

 1-2: - Basic Vector Operations:
 -------------------------------
 
 1:Add elements
 
 2:Access elements
 
 3:Change elements
 
 4:Remove elements
 
       -------------------------------
       1:  Add Elements to a Vector :
       -------------------------------
 
       vector<int>vect{1,2,3};
       vect.push_back(22);
 
 
 
 
 
 
 
       Note: We can also use the insert() and emplace() functions to add elements to a vector.
 
       -----------------------
       2:   Access elements :
       -----------------------
 
        In C++, we use the index number to access the vector elements. Here, we use the at() function to access the element from the specified index.           For example,
 
         vector<int> num {1, 2, 3, 4, 5};
         num.at(3); // means give me the number at position 3
 
 
 
 
         Note: Like an array, we can also use the square brackets [] to access vector elements. For example,

         vector<int> num {1, 2, 3};
         cout << num[1];
 
          However, the at() function is preferred over [] because at() throws an exception whenever the vector is out of bound, while [] gives a garbage           value.

          vector<int> num {1, 2, 3};

          // gives garbage value
             cout << num[4];

          // throws an exception
             cout << num.at(4);
      
        -----------------------------
        3:  Change Vector Element :
        -----------------------------
 
 
        We can change an element of the vector using the same at() function. For example,
   
          num.at(1) = 9;
          num.at(4) = 7;
 
        --------------------------------------
        4: Delete Elements from C++ Vectors :
        --------------------------------------
 
         To delete a single element from a vector, we use the pop_back() function. For example,
 
          // remove the last element
             prime_numbers.pop_back();
      
1-3: C++ Vector Functions
-------------------------
 
 In C++, the vector header file provides various functions that can be used to perform different operations on a vector.
 
1:size()	returns the number of elements present in the vector
 
2: clear()	removes all the elements of the vector
 
3: front()	returns the first element of the vector
 
4: back()	returns the last element of the vector
 
5: empty()	returns 1 (true) if the vector is empty
 
6: capacity()	check the overall size of a vector
 
 1-4: C++ Vector Iterators:
 ---------------------------
 
 Vector iterators are used to point to the memory address of a vector element. In some ways, they act like pointers in C++.
 
 We can create vector iterators with the syntax

 vector<T>::iterator iteratorName;
 
          // iterator for int vector
 
             vector<int>::iterator iter1;

         // iterator for double vector
 
            vector<double>::iterator iter2;

