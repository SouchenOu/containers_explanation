# containers_explination





To remember:
-----------

What is template:
-----------------

A function template in c++ is a single function template that works with multiple data types simultaneously, but a standard function works only with one set of data types.

                          C++ Function Template Syntax

                          template<class T>
                          
                          T func-name(parameter list)
                          {
                              //body of the function
                          }


There are two ways we can implement templates:

1: Function Templates

2: Class Templates

Similar to function templates, we can use class templates to create a single class to work with different data types.

  Class Template Declaration:
  
  A class template starts with the keyword template followed by template parameter(s) inside <> which is followed by the class declaration.

               template <class T>
               
               class className 
               {
                 private:
                      T var;
                      ... .. ...
                 public:
                      T functionName(T arg);
                       ... .. ...
              };

In the above declaration, T is the template argument which is a placeholder for the data type used, and class is a keyword.


Once we've declared and defined a class template, we can create its objects in other classes or functions (such as the main() function) with the following syntax

className<dataType> classObject;
  
For example,

className<int> classObject;
  
className<float> classObject;
  
className<string> classObject;





Operators that can be overloaded
---------------------------------

Binary Arithmetic     ->     +, -, *, /, %

Unary Arithmetic     ->     +, -, ++, —

Assignment     ->     =, +=,*=, /=,-=, %=

Bit- wise      ->     & , | , << , >> , ~ , ^

De-referencing     ->     (->)

Dynamic memory allocation and De-allocation     ->     New, delete 

Subscript     ->     [ ]

Function call     ->     ()

Logical      ->     &,  | |, !

Relational     ->     >, < , = =, <=, >=




--------------------------------------------------------------------------------------------------------------------------------------------------------



What is a data structures:
--------------------------


A data structure is not only used for organizing the data. It is also used for processing, retrieving, and storing data. There are different basic and advanced types of data structures that are used in almost every program or software system that has been developed. So we must have good knowledge about data structures. 



<img width="703" alt="Screen Shot 2023-01-23 at 1 59 03 PM" src="https://user-images.githubusercontent.com/87101785/214045796-98d957b9-9532-4643-8e59-b0d5ed2a3543.png">






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


namespace in C++
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
    
    
std::allocator() in C++
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

Allocators :

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
                  
 typedef in C++
 ---------------
                  
typedef keyword in C++ is used for aliasing existing data types, user-defined data types, and pointers to a more meaningful name.                 
                  
The typedef in C/C++ is a keyword used to assign alternative names to the existing datatypes. It is mostly used with user-defined datatypes when the naming of the predefined datatypes becomes slightly complicated to use in programs.                 
                  
  
 
 The keyword typename:
 ---------------------
 
The keyword typename was introduced to specify that the identifier that follows is a type. Consider the following example:

                      template <class T>
                      Class MyClass
                      {
                         typename T::SubType * ptr;
                            ...
                      };
Here, typename is used to clarify that SubType is a type of class T. Thus, ptr is a pointer to the type T::SubType. Without typename, SubType would be considered a static member. Thus

                        T::SubType * ptr
 
would be a multiplication of value SubType of type T with ptr.
 
 
 Use of explicit keyword in C++ :
 ------------------------------
 
Explicit Keyword in C++ is used to mark constructors to not implicitly convert types in C++. It is optional for constructors that take exactly one argument and work on constructors(with a single argument) since those are the only constructors that can be used in typecasting.
 

                 class String 
                 {
                     public:
                         String(int n); // allocate n bytes to the String object
                         String(const char *p); // initializes object with char *p
                 };
Now, if you try:

                      String mystring = 'x';
 
The character 'x' will be implicitly converted to int and then the String(int) constructor will be called. But, this is not what the user might have intended. So, to prevent such conditions, we shall define the constructor as explicit:

                 class String 
                 {
                    public:
                         explicit String (int n); //allocate n bytes
                         String(const char *p); // initialize sobject with string p
                 };
 
 
 
 
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
 
 
 
vector::vector (constructors)
 ----------------------------
 
1:    explicit vector (const allocator_type& alloc = allocator_type());

2:    explicit vector (size_type n, const value_type& val = value_type(),const allocator_type& alloc = allocator_type());

3:    vector (const vector& x);
 
 
                  
                  alloc: Allocator object,The container keeps and uses an internal copy of this allocator.
                  Member type allocator_type is the internal allocator type used by the container, defined in vector as an alias of its second template                   parameter (Alloc).
                  If allocator_type is an instantiation of the default allocator (which has no state), this is not relevant.
                  
                  n: Initial container size (i.e., the number of elements in the container at construction). 
                  Member type size_type is an unsigned integral type.
 
                  val: Value to fill the container with. Each of the n elements in the container will be initialized to a copy of this value.
                  Member type value_type is the type of the elements in the container, defined in vector as an alias of its first template parameter                       (T).


 
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

           1: Initialize Vector Iterators
           ------------------------------
 
           We can initialize vector iterators using the begin() and end() functions.
            
                  begin() function:
                  ------------------

                  The begin() function returns an iterator that points to the first element of the vector. For example,

                  vector<int> num = {1, 2, 3};
                  vector<int>::iterator iter;

                  // iter points to num[0]
                  iter = num.begin();
 
                 end() function:
                 ---------------

                 The end() function points to the theoretical element that comes after the final element of the vector. For example,

                 // iter points to the last element of num
                 iter = num.end() - 1;

 
 
 
 vector class:
 -------------
 
The C++ Standard Library vector class is a class template for sequence containers. A vector stores elements of a given type in a linear arrangement, and allows fast random access to any element. A vector is the preferred container for a sequence when random-access performance is at a premium.
 
 
      ---------
      Syntax:
      ---------
 
 
      C++


          template <class Type, class Allocator = allocator<Type>>
          class vector
          {
              ----
          }
 
      -----------
      Parameters:
      -----------
 
 
         Type:  The element data type to be stored in the vector

         Allocator: The type that represents the stored allocator object that encapsulates details about the vector's allocation and deallocation of              memory. This argument is optional and the default value is allocator<Type>.

 
       ---------
       Members:
       ---------
 
       1:Constructors
 
        vector	Constructs a vector of a specific size or with elements of a specific value or with a specific allocator or as a copy of some other                 vector.
       
 
       ---------
       Typedefs:
       ---------
     
 
        1-[allocator_type](#allocator_type):   A type that represents the allocator class for the vector object.
        ------------------------------------
 
        2-const_iterator:   A type that provides a random-access iterator that can read a const element in a vector.
        -----------------
 
        3-const_pointer:   A type that provides a pointer to a const element in a vector.
        ---------------
 
        4-const_reference:   A type that provides a reference to a const element stored in a vector. It's used for reading and doing const operations.
        -----------------
 
        5-const_reverse_iterator:   A type that provides a random-access iterator that can read any const element in the vector.
        ------------------------
 
        6-difference_type:   A type that provides the difference between the addresses of two elements in a vector.
        -----------------
 
        7-iterator:   A type that provides a random-access iterator that can read or modify any element in a vector.
        ----------
 
        8-pointer:   A type that provides a pointer to an element in a vector.
        ---------
 
        9-reference:   A type that provides a reference to an element stored in a vector.
        -----------
 
        10-reverse_iterator:   A type that provides a random-access iterator that can read or modify any element in a reversed vector.
        --------------------
 
        11-size_type:   A type that counts the number of elements in a vector.
        -------------
 
        12-value_type:   A type that represents the data type stored in a vector.
        -------------
 
 
 
        -----------
        Functions:
        -----------
 
 
                 assign:	Erases a vector and copies the specified elements to the empty vector.
                 ------
                 at:	Returns a reference to the element at a specified location in the vector.
                 --
                 back:	Returns a reference to the last element of the vector.
                 ----
                 begin:	Returns a random-access iterator to the first element in the vector.
                 -----
                 capacity:	Returns the number of elements that the vector could contain without allocating more storage.
                 --------
                 cbegin:	Returns a random-access const iterator to the first element in the vector.
                 ------
                 cend:	Returns a random-access const iterator that points just beyond the end of the vector.
                 ----
                 crbegin:	Returns a const iterator to the first element in a reversed vector.
                 -------
                 crend:	Returns a const iterator to the end of a reversed vector.
                 -----
                 clear:	Erases the elements of the vector.
                 -----
                 data:	Returns a pointer to the first element in the vector.
                 -----
                 emplace:	Inserts an element constructed in place into the vector at a specified position.
                 -------
                 emplace_back:	Adds an element constructed in place to the end of the vector.
                 -------------
                 empty:	Tests if the vector container is empty.
                 ------
                 end:	Returns a random-access iterator that points to the end of the vector.
                 ----
                 erase:	Removes an element or a range of elements in a vector from specified positions.
                 ------
                 front:	Returns a reference to the first element in a vector.
                 -----
                 get_allocator:	Returns an object to the allocator class used by a vector.
                 ---------------
                 insert:	Inserts an element or many elements into the vector at a specified position.
                 ------
                 max_size:	Returns the maximum length of the vector.
                 --------
                 pop_back:	Deletes the element at the end of the vector.
                 ---------
                 push_back:	Add an element to the end of the vector.
                 ---------
                 rbegin:	Returns an iterator to the first element in a reversed vector.
                 ------
                 rend:	Returns an iterator to the end of a reversed vector.
                 -----
                 reserve:	Reserves a minimum length of storage for a vector object.
                 --------
                 resize:	Specifies a new size for a vector.
                 -------
                 shrink_to_fit:	Discards excess capacity.
                 --------------
                 size:	Returns the number of elements in the vector.
                 ----
                 swap:	Exchanges the elements of two vectors.
                 ----
 
 
 Some of functions  i used it to implement vector functions: 
 -----------------------------------------------------------
 
 1 - destroy(): 
 
In C++, the operator delete destroys an object by calling its destructor, and then deallocates the memory where that object was stored. Occasionally, however, it is useful to separate those two operations. [1] Destroy calls an object's destructor without deallocating the memory where the object was stored.
 
 we use it to Change size
 
                           void resize (size_type n, value_type val = value_type());

 
Resizes the container so that it contains n elements.

If n is smaller than the current container size, the content is reduced to its first n elements, removing those beyond (and destroying them).

If n is greater than the current container size, the content is expanded by inserting at the end as many elements as needed to reach a size of n. If val is specified, the new elements are initialized as copies of val, otherwise, they are value-initialized.

If n is also greater than the current container capacity, an automatic reallocation of the allocated storage space takes place.

Notice that this function changes the actual content of the container by inserting or erasing elements from it.
 
2 - construct():
 
 
                         void construct( pointer p, const_reference val );
 
this function provides the automatic fall back to placement new, the member function construct() is an optional Allocator requirement since C++11. 
 
The function constructs an object of member type value_type (an alias of allocator's template parameter) using its copy constructor to initialize its value to a copy of val, as if the following code was used:
new ((void*)p) value_type (val);
 
 
 
3 - allocate() :
 
 
                       pointer allocate (size_type n, allocator<void>::const_pointer hint=0);

 
Attempts to allocate a block of storage with a size large enough to contain n elements of member type value_type (an alias of the allocator's template parameter), and returns a pointer to the first element.
 
In the standard default allocator, the block of storage is allocated using ::operator new one or more times, and throws bad_alloc if it cannot allocate the total amount of storage requested.




4 - deallocate() :


                      void deallocate (pointer p, size_type n);

Releases a block of storage previously allocated with member allocate and not yet released.

The elements in the array are not destroyed by a call to this member function.

In the default allocator, the block of storage is at some point deallocated using ::operator delete (either during the function call, or later).

 5 - distance() :
 
The distance() function in C++ helps find the distance between two iterators. In other words, we can use this function to calculate the number of elements present between the two iterators. This function is available in the <iterator> header file.






The difference between size , max_size and capacity :
-----------------------------------------------------


----size:

Returns the number of elements in the vector container.

This is the number of actual objects held in the vector, which is not necessarily equal to its storage capacity. Vectors automatically reallocate their storage space when needed or when requested with member resize. To retrieve the current storage capacity of a vector you can call to its member capacity.

----capacity:

Returns the size of the allocated storage space for the elements of the vector container.

Notice that, in vectors, the capacity is not necessarily equal to the number of elements that conform the underlying vector content (this can be obtained with member vector::size), but the capacity of the actual allocated space, which is either equal or greater than the content size.

Notice also that this capacity does not suppose a limit to the size of the vector. If more space is required to accomodate new elements in the vector, the capacity is automatically expanded, or can even be explicitly modified by calling member vector::reserve.

The real limit on the size a vector object can reach is returned by member vector::max_size.

----max_size:

Returns the maximum number of elements that the vector container can hold.

This is not the amount of storage space currently allocated to the vector (this can be obtained with member vector::capacity), but the maximum potential size the vector could reach due to system or library implementation limitations.







Integral Types
---------------
  
  
  
Fundamental types in C++ are divided into three categories: integral, floating point, and void. Integral types are capable of handling whole numbers. Floating point types are capable of specifying values that may have fractional parts. The void type describes an empty set of values.

The category integral includes the following datatypes -

char

bool

short

int

long

long long

wchar_t, __wchar_t

  
The category floating point includes the following datatypes -
  

float

double

long double
  

In C, an integral type can declare :

Integer values, signed or unsigned

Boolean values, where 0 is equivalent to false and any nonzero number is equivalent to true

Characters, which are automatically converted to an integer value by the compiler

Members of an enumerated type, which are interpreted as an integer by the compiler

Bit fields

The integral types are:

char , signed char , unsigned char -8 bits

short int , signed short int , and unsigned short int -16 bits

int , signed int , and unsigned int -32 bits

long int , signed long int , and unsigned long int -32 bits (OpenVMS)

long int , signed long int , and unsigned long int -64 bits (Digital UNIX)

signed __int64 (Alpha) and unsigned __int64 (Alpha)-64 bits

enum -32 bits


class template <iterator> std::iterator :
----------------------------------------

An iterator is any object that, pointing to some element in a range of elements (such as an array or a container), has the ability to iterate through the elements of that range using a set of operators (with at least the increment (++) and dereference (*) operators).\


Iterator operations:


advance :	Advance iterator (function template).

distance :	Return distance between iterators (function template)

begin :	Iterator to beginning (function template).

end :	Iterator to end (function template).

prev:	Get iterator to previous element (function template).

next:	Get iterator to next element (function template).


Iterator generators:

back_inserter:	Construct back insert iterator (function template)

front_inserter:	Constructs front insert iterator (function template)

inserter:	Construct insert iterator (function template)

make_move_iterator:	Construct move it

  
  2: Map:
  -------
  
  
  
  
  
  ----------------- ----------------- Additional functions :----------------- ----------------- ----------------- -----------------
  ------------------------------------------------------------------------------------------------------------------
  
  enable_if() :
  -------------
  
  
  Le trait enable_if est une technique permettant de contrôler l'application de SFINAE.
  
Sa signature est enable_if<bool,T=void> ce qui signifie qu'il est défini sur la base d'une condition statique de d'un type (qui sera void par défaut)
L'expression std::enable_if<true,T>::type équivaut à T
L'expression std::enable_if<false,T>::type est indéfinie (le type résultant est incomplet), ce qui peut (selon les circonstances) éliminer un template de ceux examinés pour la génération du code ou tout simplement bloquer la compilation
  
  
pair :
-----

The C++ pair container is a basic header container that holds two data elements or objects. The order is set, and it refers to the first element as "first." It refers to the second element as "second" (first, second).
  
 
A pair is a term that is used to combine two values that may or may not be of the same kind. The C++ pair allows you to store two disparate items as a single entity.
 
 
 
 
          example 1:
          ---------
 
          int main()

          {

               pair<int, char> PAIR1; 

               PAIR1.first = 100;

               PAIR1.second = 'G';

               cout << PAIR1.first << " ";

               cout << PAIR1.second << endl;

               return 0;

          }
  
        example 2:
        ---------
  
  

          int main()

          {

                pair<string, double> PAIR2("GeeksForGeeks", 1.23);

                cout << PAIR2.first << " ";

                cout << PAIR2.second << endl; 

                return 0;

          }
          
  
  https://www.geeksforgeeks.org/pair-in-cpp-stl/
  
 ----------------- ----------------- ----------------- ----------------- ----------------- ----------------- ----------------- -----------------

  AVL tree :
  ---------
  
  AVL Tree can be defined as height balanced binary search tree in which each node is associated with a balance factor which is calculated by subtracting the height of its right sub-tree from that of its left sub-tree.
  
  1: It is a binary search tree (BST) (one more important  point in binary search tree we cant find duplicated element)
  
  2:For each node in the tree the difference between the hight of left subtree and the height of left subtree is (-1 or 0 or 1)
  
  for each node balance factor most be calculater
  
  
  


1: binary search tree
-------------------




In computer science, a binary search tree (BST), also called an ordered or sorted binary tree, is a rooted binary tree data structure with the key of each internal node being greater than all the keys in the respective node's right subtree and less than the ones in its left subtree.

https://www.youtube.com/watch?v=cySVml6e_Fc

<img width="182" alt="Screen Shot 2023-02-04 at 1 41 22 PM" src="https://user-images.githubusercontent.com/87101785/216768260-b370b59b-483d-4d8a-ae41-3e8bacb2c077.png">


  
1.1 Insert binary search tree:
------------------------------
  
<img width="636" alt="Screen Shot 2023-02-04 at 1 49 24 PM" src="https://user-images.githubusercontent.com/87101785/216768597-872d0319-5ab8-4c99-b6d7-ed762aaa6384.png">

How to delete data from BST :
  
 In this case we can have tree situations :
  
  1: maybe that node have 0 children !
  
  2: Maybe that node can have one child !
  
  3: Maybe that node you want to delete have 2 children !
  
  
  
  1--for first situation --> simply we delete that node and free it 
  
  2--for second situation --> so that node will be replace with his children maybe the left one or the right one
  
  <img width="351" alt="Screen Shot 2023-02-04 at 2 42 37 PM" src="https://user-images.githubusercontent.com/87101785/216770926-4ddd5225-2273-443d-9364-e1fa5d775824.png">
  
  As you see here node 4 willl be replace by node 5
  
  3--for the last situation --> suppose we want to delete node 11 
  
  <img width="261" alt="Screen Shot 2023-02-04 at 2 44 02 PM" src="https://user-images.githubusercontent.com/87101785/216770994-ca520845-1de1-4fb2-ab95-8333a66b8535.png">

so we will replace node 11 by each number ?!!
  
  --here we have 2 situations:
  
  1: we can replace the node being deleted with its inorder predecesser
  
  2: we can replace the node being deleted with its inorder successer.
  
  
🌱 first situation:
  
  inorder predecesser would be : the largest element from the left subtree that node you want to delete (in this example the largest element in the left subtree is node 10)

  
  <img width="261" alt="Screen Shot 2023-02-04 at 2 57 35 PM" src="https://user-images.githubusercontent.com/87101785/216771604-22d9aead-3188-4edf-b527-0061bb617d5e.png">

  ---->so we can replace node 11 with node 10
  
  <img width="487" alt="Screen Shot 2023-02-04 at 3 00 27 PM" src="https://user-images.githubusercontent.com/87101785/216771716-cc4471f9-e855-4d9b-8569-10c60018b9ae.png">

 
 🌱 second situation:
  
  inorder successor would be : the smallest element from the right subtree of that node (in this example the smallest element is node 17)
  
  <img width="555" alt="Screen Shot 2023-02-04 at 3 04 38 PM" src="https://user-images.githubusercontent.com/87101785/216771951-d7ce7016-08c0-4d42-ad6b-715325eab5b1.png">

  
  
  
  
 1.2 How to construct a binary search tree when only preorder is given : 
 ------------------------------------------------------------------------------------
  
  preorder : 20,16,5,18,17,19,60,85,70 (Root left right). --> here the first on is the root (node 20)
  
  Inorder : 5,16,17,18,19,20,60,70,85 (Left root right) --> here the middle one is the root (node 20)
  
  
  <img width="599" alt="Screen Shot 2023-02-04 at 3 34 11 PM" src="https://user-images.githubusercontent.com/87101785/216773156-e6408138-684b-4751-9c26-baeac9147904.png">

  
  
  <img width="722" alt="Screen Shot 2023-02-04 at 3 43 21 PM" src="https://user-images.githubusercontent.com/87101785/216773559-3591c892-32c6-404f-8ca9-3b5d899156d4.png">

  by using inorder we divise the number to dicide which the number will be in the right and which one will be in the left
  
  by using preorder wich one is the root of each subtree
  
  
    so this is our binary search tree ;

  <img width="1208" alt="Screen Shot 2023-02-04 at 3 48 34 PM" src="https://user-images.githubusercontent.com/87101785/216773794-4c34f4ca-e5dc-476d-b14f-571c5f3d7c77.png">

  
1.3:   How to construct a binary search tree when only postorder is given :
----------------------------------------------------------------------------
  
  
  
  postorder--> 5,17,19,18,16,70,85,60,20 (Left ,Right, root)
  
  so firstly we should write inorder tree-> 5,16,17,18,19,20,60,70,85 (Left, Right, Root)(from the smallest to the greatest)
  
  
  so here by using postorder we can find the root element that is node 20 (the last one)
  
  
  
  
  Here to find the root we use postorder.
  
  and to find wich one the left and the right of that root we use inorder .
  
  
  
What is red_black_tree :
------------------------

  we know that trees is a Data structure (data structure is a way for orgnising the data (we can insert, update data or delete data ... in a less time ))
 
  in binary search tree (insertion or deletion is going to take o(log2n) log n time in average case ) --> time complexity = o(log2n) not o(n)
  that why our tree should be a balance tree (if the tree is balance the time complicity will be less )
  
  --->AVL trees  is balanced than red black trees but red black trees guaranties that the time complicity will be less 
  
  
In computer science, a red–black tree is a kind of self-balancing binary search tree. Each node stores an extra bit representing "color" ("red" or "black"), used to ensure that the tree remains balanced during insertions and deletions.

  
Introduction:

When it comes to searching and sorting data, one of the most fundamental data structures is the binary search tree. However, the performance of a binary search tree is highly dependent on its shape, and in the worst case, it can degenerate into a linear structure with a time complexity of O(n). This is where Red Black Trees come in, they are a type of balanced binary search tree that use a specific set of rules to ensure that the tree is always balanced. This balance guarantees that the time complexity for operations such as insertion, deletion, and searching is always O(log n), regardless of the initial shape of the tree.

Red Black Trees are self-balancing, meaning that the tree adjusts itself automatically after each insertion or deletion operation. It uses a simple but powerful mechanism to maintain balance, by coloring each node in the tree either red or black. 

-->Red black tree it is a binary search tree

💬 Rules That Every Red-Black Tree Follows: 

1:Every node has a color either red or black.

2:The root of the tree is always black.

3:There are no two adjacent red nodes (A red node cannot have a red parent or red child).

4:Every path from a node (including root) to any of its descendants NULL nodes has the same number of black nodes.

5:Every leaf (e.i. NULL node) must be colored BLACK.

  
  
  
  --> it is a self balancing BST (binary search tree)->means it balanced it self
  
  --> every node is red or black 
  
  --> root is alwase black 
  
  --> every leaf which is NIL is black (that node doesnt appear it is the shild of the last each node in our tree)
  
  --> if node is red then its children are black 
  
  --> each path to NULL node should  have the same number of black nodes .
  
  
  <img width="304" alt="Screen Shot 2023-02-04 at 6 50 23 PM" src="https://user-images.githubusercontent.com/87101785/216782081-bd28d3da-8622-4968-9f57-cb6cf5c2c514.png">
  

  
  
  
  
  
  <img width="703" alt="Screen Shot 2023-01-21 at 2 49 37 PM" src="https://user-images.githubusercontent.com/87101785/213869901-557ec6ee-473c-4b06-a6bf-87eccb31a3a9.png">
  
  

 
  
  
  
  
  
  
  
  
  
  
  
  
  
  Some informations about binary serch tree (BST) :
  ---------------------------------------
  
  -All the left node should be less than the Root node.
  
  -All the right node should be greater than the root node.
  
  -The left node should be less than the previous node.
  
  -The right node should be greater than the previous node.
  
  
  -In binary search tree (The searching, deletion , insertion is going to take order f log in time O(log 2 n) in average case but in worst case is it O (n))

  so searching about  a data using red-black-tree it is going to take less time... that is why we use red-black-tree
  

  
In computer science, a binary search tree (BST), also called an ordered or sorted binary tree, is a rooted binary tree data structure with the key of each internal node being greater than all the keys in the respective node's left subtree and less than the ones in its right subtree. The time complexity of operations on the binary search tree is directly proportional to the height of the tree.






-----------------------------------------------------------------------------------------------------------------------------------------------



some resources:
 -------------
 
 
 https://cplusplus.com/reference/vector/vector/vector/
 
 https://learn.microsoft.com/en-us/cpp/standard-library/allocator-class?view=msvc-170
 
 https://learn.microsoft.com/en-us/cpp/standard-library/vector-class?view=msvc-170
 
 https://www.geeksforgeeks.org/how-to-implement-our-own-vector-class-in-c/
 
 https://codereview.stackexchange.com/questions/255149/stdvector-allocator-aware-implementation
 
 https://www.qnx.com/developers/docs/6.5.0SP1.update/com.qnx.doc.dinkum_en_cpp/lib_cont.html
 
 https://www.qnx.com/developers/docs/6.5.0SP1.update/com.qnx.doc.dinkum_en_cpp/vector.html#vector
 
 https://learn.microsoft.com/en-us/cpp/standard-library/allocator-traits-class?view=msvc-170
 
 https://docs.ros.org/en/foxy/Tutorials/Advanced/Allocator-Template-Tutorial.html

https://docs.microsoft.com/en-us/cpp/standard-library/allocators?view=msvc-170

https://www.codeproject.com/Articles/4795/C-Standard-Allocator-An-Introduction-and-Implement


topic=SSGH3R_12.1.0/com.ibm.xlcpp121.aix.doc/standlib/stl_vector.html

https://docs.microsoft.com/en-us/cpp/standard-library/vector-class?view=msvc-170

https://iq.opengenus.org/implement-binary-search-tree-in-cpp/


iterators :

https://www.internalpointers.com/post/writing-custom-iterators-modern-cpp

https://anderberg.me/2016/07/04/c-custom-iterators/
  
 https://cplusplus.com/reference/iterator/iterator/


enable_if : 

https://eli.thegreenplace.net/2014/sfinae-and-enable_if/

https://www.youtube.com/watch?v=mNxAqLVIaW0&t=672s

https://learn.microsoft.com/en-us/cpp/standard-library/enable-if-class?view=msvc-170


Sentinel node :


https://en.wikipedia.org/wiki/Sentinel_node

rbt : https://www.cs.usfca.edu/~galles/visualization/RedBlack.html

https://en.wikipedia.org/wiki/Red%E2%80%93black_tree#Insertion
  
  
 STL Implementations:
  
  
  https://azrael.digipen.edu/~mmead/www/Courses/CS270/STLImplementations.html
  
  
  https://www.codeproject.com/Articles/36530/An-Introduction-to-Iterator-Traits
  
  
  https://www.youtube.com/watch?v=F9eDv-YIOQ0
