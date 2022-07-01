# JAVA

**Class** : A class is a user defined blueprint or prototype from which objects are created which are having common set of properties.

- The variables inside a method needs to be intialized, else we will get a compiler error. But there is no compulsion to initialize the class variables, and if we try to print the class variables then we will get the default values of that specific data type.

**Object** : An object is an instance of a class which has common set of properties, state, behaviour and identity. State is an attribute, Behaviour is a method. When an object is created for a class then that class is said to be instantiated.

**Constructor** : Constructors are used to assign values to the class variables at the time of object creation. A constructor can't be final, abstract, static and synchronised.

 → this() is used to call a method from that class itself.

 → Super() is used to call a overridden method of parent class from child class.

- The default constructor initializes the instance variables declared in the class. When class has only constructors with parameters then the compiler does not create a default constructor.

**Static** : Wherever a method or variable is declared with static keyword then that method or variable belongs to that class itself instead of the instance of the class. Hence these methods can be accessed directly with the help of class without creating an object.Static keyword allows the JVM to access the main method without creating an object.

Main() : Main method in java is the entry point for the JVM into the program. JVM launches the program by invoking the main method.

String [] args : When a program is executed, if need to pass data to the program through command line then the array of sequence of characters are passed to the main function by JVM. Which is stored in the String[] args which is an array of strings named args.

- Object oriented programming is a programming paradigm based on the concept of "objects", where functions and data are bind together as a single entity called objects.

**Inheritance** : It is a mechanism in which one class is allowed to inherit the features of another class. Main reason: reusability.
Extends keyword is used to inherit a class. Whenever a class which extends another class, and if we create an object for the subclass, then the constructor of parent class will be called.

**Encapsulation** : It is designed as wrapping the data under single unit. It is a mechanism that binds the code and data together. It also restricts the direct access of the objects components.
Main reason: data hiding

**Polymorphism** : Many forms. It is an ability to display a msg in different ways

     1. Compile time (overloading) 2. Run time (overriding)

**Abstraction**: Hiding the implementation details and only showing the essentials for the user. It can be acheived using abstract class or an interface. Abstract class are the classes that can have abstract methods as well as normal methods. If a method in a class is abstract then the class must be abstract. Abstract modifiers can be used with non-static fields and class.

- Access modifiers : private < default < protected < public

**Interface** : Similar to class, it contains methods and variables. Methods declared in an interface is by default abstract, and static and default methods can have body. If an interface contains only one abstract method, but any number of default or static methods then that interface is called funtional interface.

- Similarly, if there is an interface with no methods, then it is called marker interface. Variables inside an interface needs to declared, because they final static.

Type casting : Assigning values of one type to other type.
 => Upcasting : Type casting the child object to a parent object. The way of treating the object of child class to be an object of parent class.
Summarily downcasting

## String, StringBuilder, StringBuffer

- String is nothing but sequence of characters, which is immutable, and are stored in string constant pool of heap memory. If we create a string and if we create another string variable with same value, then JVM checks the string constant pool and if the values are same then it points to variable to the previously created string object. That is why we can use equals() and '==' on a string literal. And String class overrides the equals() method of object class.

- StringBuilder and StringBuffer are mutable Strings, when ever we want to acheive mutability in strings we have to use either of these two. These classes does not override the equals() of object class, it is as same as '==' when we use these classes. To compare two strings of stringBuilder or Buffer we havw to convert them to string using toString() and then we have to use equals().

- When to use Builder and Buffer? StringBuffer is used in multi-thread environments because it is thread-safe. We can also use Builder in multi-thread environment but it will provide errorness output.

- '==' Is an operator and .equals() is a method, whereas == checks if both objects point to same memory location or not and .equals() compares values in the string object.

## Exception Handling

- This is the most important concept of java. Java is robust because it can handle the exceptions. Exception is an event where the program terminates abruptly. To avoid those abrupt terminations we have to use Exception handling. It also helps us to override the system generated messages and we can write our own message, so that the end user can understand what went wrong.

 Exception handling contains 5 keywords, they are.

- try : This is the place where the code for exception needs to be written.

- catch : this is preceeded by the try block, which helps us to catch the exception that is thrown by try block. If we don't know the error that try block throws, then we can write the parent class for exception in catch, i.e catch(Exception e) {} but writting the parent class exception is recommended, so always use exception that will occur. If we are catching multiple exceptions then writing the parent class at the top and child class below will throw a complier error.

- finally : this block is used to close the resources that are opened to take the user inputs, and it is recommended that we have to close the resources always. Anything that is inside the finally will execute, irrespective of the occurance of exception.

- Throw : Throw keyword is used to throw an exception explicitly and can only able to throw single exception and is used with in the method.

- Throws : Throws keyword is used to throw multiple exceptions and used with the method signature, It is declared to show that a statement or method might throw an exception.

There are two types of exceptions. They are,
Runtime exception and compile time exception

- Runtime exceptions are also called as unchecked exceptions, which occurs due to mistake of programmer.
  Examples of runtime exception are : Arithmetic, IndexOutOfBounds, ClassCastException, IllegalArgumentException(NumberFormatException), NullPointerException.

  ClassNotFoundException : This Exception is raised when we try to access a class whose definition is not found

- Compile time exception, which is also known as checked exceptions, these exceptions need to be catched at the time of compilation.
  Examples of compile time are : FileNotFound, most of the IOexceptions are compile time exceptions.

- Don't catch a checked exception that could not be thrown, if we try to do so, it will throw a compile time error and in case of unchecked exception it won't cause any problem.

- Try with resources : Try with resources is nothing but a try statement with multiple resources, that are closed with it. Resources is nothing but an object. Try block ensures to close the resource at the end of the statement. Resource is an object that must be closed with the program. We cannot add any other class in the try with resources block, the classes that implements java.io.AutoClosable or closable can only be used.

OOP
Object oriented programming is about objects which contains both data and code. Data in the form of fields and code in the form of methods.

System.out.println();
System is a class where out is an object of printstream class which is static and println() is an instance method of printstrean class.

## Overriding with exception handling

 1.While overriding a method we can only throw unchecked expection in the method signature, if the parent class method does not have any throws in the method signature, unchecked exceptions are also known as runtime exception.

- Examples of runtime exception are : Arithmetic, IndexOutOfBounds, ClassCastException, IllegalArgumentException(NumberFormatException), NullPointerException.

 2.But if the parent method has throws in the method signature, we can use checked expection in overriden method in subclass. Checked exceptions are also known as compile time exceptions.

- Examples of compile time are : FileNotFound, most of the IOexceptions are compile time exceptions.

### OVERRIDE

- When ever a static method is overriden in the subclass with exact same method signature, then if we creat an object and call that method parent class method will gets called, because there is no use of overriding a static method.
- If we try to override a static method in the subclass without the static keyword, then that method will throw compiler error.When methods of parent class are overriden, and if we create an object for the subclass with downcasting, then the subclass method will gets called.

- How does static block executes even before main method ?
After compilation the source code is converted to class file or bytecode. This bytecode is loaded to JVM, at the time of loading to JVM the static block is executed and the main method will be executed after loading to JVM. And that is becuase the static block is stored in the memory at the time of class loading and executed even before the object creation.
The order of execution is Static block > static method > static variables.

**Singleton class**: Singleton class is a class which can have only one object at a time. If we try to instantiate a new object it will also point to the first instance created. The main purpose of the singleton class is to limit the object creation.

- The difference between normal class and singleton class is in object creation. Where a normal object created using constructor and object in singleton is created using getInstance() method.

**Thread-safety**: Thread-saftey is a term used to inform that if a method is safe to use with in the multi-thread environment without any side effects.

- Thread safe means a method or process can work properly in a multithreaded environment without any side effects.
- When the scope of a reference variable is limited within a method then that method is said to be thread safe, because every thread has its own stack.
When multiple threads are accessing an object or working on the same data at the same time, then we will get inconsistent results and it is not thread safe.

**Multi-Threading** : Multi threading is a process of executing multiple threads at a time to maximize the cpu utilization. Multiple applications execute two or more threads concurrently which is also known as concurrency, threads run parallel to each other and they does not allocate separate memory. Also, context switching takes less time in multithreading.

- Advantages of multithreading
Threads are independent and we can perform multiple operations at a time, as they are independent other threads won't get effected if one thread meets an exception.
When thread is working on an object and preventing the other thread from accessing the method or data at the same time, it is said to be thread safe.We can achieve thread safety by using keywords like synchronisation, volatile, atomic and final.

:exclamation: Local variables are never shared between threads, they are stored in each thread's own stack.

**DeadLock** : It is a situation where two or more threads are blocked forever waiting for the object lock, which is acquired by the other thread and the second thread is waiting for the object lock acquired by the first thread, Each of them are waiting for other to release the lock.

**Synchronised**
This keyword is used to make the class or method thread-safe, which means only one method can have lock on synchronised method and use it.Other threads have to wait till lock is released.

**Thread pool**
Thread pool is nothing but managing multiple threads at a time, thread pool reuses the threads that are previously created to perform current tasks, which also solves the problem of memory consumption on creating a new thread. It also eliminates the delay introduced in creating a thread for every new task, making the application more responsive.

Problems of thread pool

- Thread leakage occurs when a thread is removed from the pool to execute a task, but doesn't return after the task is completed.If this process occurs repeatedly, eventually all the threads will be removed and thread pool will be emptied and no threads will present to execute other tasks.
- It introduces another problem called resource thrashing when the pool size is very large then the time is wasted in context switching between threads.Having more threads cause starvation problem leading to resource thrashing.
- Many multi-threading environments have a deadlock situation, whereas in thread pool there is another kind of deadlock where one in which all the executing threads are waiting for the results from blocked threads waiting in the queue due to unavailability of threads for execution.

There are various thread pools in java:

- Single Thread Executor: A thread pool with only one thread. So all the submitted tasks will be executed sequentially. Method :Executors.newSingleThreadExecutor()
- Cached Thread Pool: A thread pool that creates as many threads it needs to execute the task in parrallel. The old available threads will be reused for the new tasks. If a thread is not used during 60 seconds, it will be terminated and removed from the pool.
  Method :Executors.newCachedThreadPool()
- Fixed Thread Pool: A thread pool with a fixed number of threads. If a thread is not available for the task, the task is put in queue waiting for an other task to ends.
  Method :Executors.newFixedThreadPool()
- Scheduled Thread Pool : A thread pool made to schedule future task.
  Method :Executors.newScheduledThreadPool()
- Single Thread Scheduled Pool: A thread pool with only one thread to schedule future task. Method :Executors.newSingleThreadScheduledExecutor()

Difference between thread safe and synchronisation
Thread safe means a process can handle multiple or concurrent requests at a time, without any side effects.
Synchronised means one by one which means only one thread can access a method at a time, where as to make a process thread safe we use synchronised to make it thread safe, even they act at the same time , they cannot access the method or block at a time.

## Collections

Collection is nothing but group of individual classes and interfaces that are represented as single unit. It is also known as "Collection Framework".

- Frame work is a set of classes and interfaces which provides a ready made architecture, which provides consistent API by reducing programming effort.
- Iterable interface is the root interface of collection framework. The main function of iterable interface is to provide an iterator for collections. It has only one abstract method, Iterator iterator();

- Collection is an interface which extends the iterable interface.

- List interface: It extends the Collection interface, which is used to store the data of type list in ordered manner. The classes that implement list interface are ArrayList, vector, stack.

  - ArrayList: Array list is nothing but a dynamic array whose size is not fixed. It is a bit slower than the normal arrays but are used in different types of programs.

  - Vector: Vector is similar to that of array list, the only difference is vector is synchronised and arraylist is not.

  - Linkedlist: Linked list is a implementation of list and deque interfaces. It implements all optional list operations and permits all elements.
  It is not synchronised and every element is a node, which keeps a reference to the next and previous ones, it maintains insertion order.

## Difference between list, set and queue interface

- List is an ordered collection of objects, where duplication of objects is allowed and we can perform operations on the objects anywhere in the list like adding, removing, changing.

- Queue is also ordered collection with the principle of FIFO, where the elements are added at the end and removed from the beginning. We can find how many elements are present in the queue, but we can't find at which index the element is.

- Set is an unordered linear data structure, where duplication is not allowed. We can add or remove the elements and can know how many are there, but unable to find specific element because it is not index based.

**Map Interface**

- Map interface is present in java.util package. It represents a mapping between a key and a value and it is not a subtype of collection interface.

- Sorted map is an interface which extends the map interface, Tree map is class which implements sorted map.

- Difference between hashtable and hashmap is that hashtable is synchronised and hashmap is not, but hashmap allows null key and multiple null values, whereas hashtable doesn't allow any null key or value. Hashmap is preferred over hashtable when synchronisation is not needed.

**Collections Synopsis**

- Collections is a utility class which provides predefined static methods, that performs on collections and returns collections.
- The two main interfaces of collections are collection and map
- List, Set, Queue are the interfaces that extends collection interface.

**List Interface**
Arraylist provide insertion order , index based and get() and iteration is constant time, not synchronised, dynamic resizing. The capacity of the arraylist is currentcapacity * 3/2 + 1

- LinkedList provides insertion order, duplication is allowed, add(), remove() is constant time, it doesnot support random access because elements in linked list are stored in nodes which contains its own data and address of the next element which are not in adjacent.

- Vector is similar to arraylist the only difference is vector is synchronised, and the capacity will be double when we cross the initial capacity, which is 10.

- Stack is a linear data structure which works on the principle of Last In First Out order, Stack is used when we want the elements in reverse order of the way we put them in. It also has methods like push, pop, peek, search.

**Set interface:**
HashSet implements set interface does not allow duplication, not synchronised no insertion order, add() remove() are constant time
LinkedHashSet is similar to HashSet the only difference is that LinkedHashSet provides insertion order
TreeSet it is also similar to LinkedHashSet the difference is that it doesnot allow different objects and the order is sorted

**Queue interface:**
Priority queue is the class that implements queue interface, it works on the principle of FIFO which is same as queue, but the processing is done on the basis of priority
Deque interface
The class that implements Deque is arraydeque, Deque means double ended queue, where addition and deletion can be preformed on both sides.

**Map Interface:**
Map interface is used when one wants to store the data in the form of key-value pair, map doesnot allows duplication of keys and can have duplicated values, keys are immutable.

HashMap is a class that implements map interface, HashMap doesnot allows duplication of keys, it is unordered, doesnot maintain insertion order, it allows single null key multiple null values, value can be retrived only by using key, get() and put() method operations are constant time.

HashTable is same as HashMap the difference is that HashTable is synchronised and doesnot allows any null key or values.

LinkedHashMap is same as HashMap difference is that linkedhash map provides insertion order.

TreeMap is used when you want to iterate through the keys in sorted order. Time complexity of Treemap is logrithmic.

**Comparable and Comparators**

Comparable is present in java.lang package, Comparable is an functional interface which is compareTo(). Which uses natural sorting order
it returns +ve when obj1 has to come after obj2

Comparator is present in java.util package, is used for customised sorting order.

**Fail fast and fail safe:**
Fail fast is a iterator in java collection, it throws an exception called concurrentModificationException when it is iterating the collection and another thread is trying to modify the structure by adding or removing the elements.Examples of fail fast are arraylist, hashmap etc,.

- Fail safe is a iterator in java collection, it doesn't throw any exception even though there is a modification in the structure, because it creats a clone of the object and if there is any modification occurred it will affect the cloned version rather than the original copy.Fail safe iterators are to be used when an application is using multithread environment.Examples of fail safe are CopyOnWriteArraylist, concurrrent hashmap etc.There is no word called fail safe in java docs, it is referred to as weakly consistent.

- Difference between collection interface and map interface
Collection and map interface are the two main root interfaces of collection framework. Where collections are used to store objects in array format and map stores objects in the form of key-value pair, so that duplication of keys are not allowed in map interface and keys in map are mapped to atmost one value.The other main difference between collection and map is that,we retrive a element based on the index in collections, whereas in map it is done using keys.

**Load factor:**
Load factor is a measure which decides when to increase the capacity of the map, the initial load factor is 75% of the capacity. Initial capacity of map interface is 16. Which means that it will increase the capacity when 12(16\*0.75)th key-value pair is entered.
We can define our own load factor while initializing the hashmap.
HashMap<K,V> hm = new HashMap(initialCapacity, loadFactor);
Maps have load factor because, it is the one which defines their performance, when we lower the load factor we gain the performance, but that comes with a cost of increased memory usage.
Why only maps have load factor and list doesnot?
Because, in arraylist the backing array holds only one element at each index and there is no need to have load factor.

**Synchronisation** : is about preventing concurrent access.whenever a thread is synchronised that means only one thread can access the method at a time.

**Generics**
Using generics it is possible to create classes that work with different datatypes. To achieve type saftey in collections generics are used.

Cloneable
The method clone() is present in object class which is the topmost class in java, the clone() method is made valid when the cloneable interface is implemented through a class.
There are different types of cloning. They are
Deep copy:It is like creating exact copy of the original object, where the fields are cloned, it has separate memory to store the cloned objects, that is why when we change the original object after cloning, it doesn't reflect in the cloned object.

Shallow copy:When ever we implement the default clone method we get shallow copy in which it creates an instance and copies fileds to the new object and return it as object type, we need to cast it back to our original object.Only reference gets copied not the referred objects themselves.

Yield()
it is a static method of thread class which makes the currently executing thread to stop and will give a chance for the other thread with same priority. If in case there are no threads with same priority and then the current thread will continue to execute.

**Serializable**
serialize an object means to convert the state to bytestream so that the byte stream can be reverted back into a copy of object. It c an done by implenting the java.io.Serializable interface.
Once an object is converted into byte stream we can send it over the network or save it as a file or store in a database for later usage.Deserialization is the process of converting the byte stream to object.
Where serializable interface is a marker interface, which doesn't contain any method declarartion, it is just an empty interface.
Whenever a method or variable declared static serialization is ignored, becuase, it belongs to the class and serialization can only be done on data which is specific to an instance of a class that is an object.

What is serialVersionUID?

- It is a unique id that is used to verify whether a class is loaded or not after deserialization.

File streams and Java8 streams are different
File Streams
Byte Stream provides a convenient way of handling the input and output. It is further divided into two types
InputStream: It is an abstract class of Byte stream, It is used to read the data from the source which is of any format.
OutputStream: It is also an abstract class of Byte stream, it is used to write the data to destination, which is received from the source end.
Whenever an object or a variable is declared transient, then those can't be serialized, and during the initialization of deserializing those things will have their default values for objects it is null and for datatypes it is 0.

Oop and functional prog : In java everything is an object and that object has to be associated with a class and method to work or do some stuff, we can't leave a function to be isolated in java
Where as functional programming is where we can make a function with out any restrictions with the class

**STREAMS**
A stream is a sequence of object that supports various methods which can be pipelined through to produce desired results. It is also defined as the sequence of data or continuous flow of data.It is not a data structure, and cannot store any kind of data, we cannot add or remove elements from the data, it is just operations on data.

There are two types of methods in streams.They are

- Intermediate and terminal methods

  - Intermediate methods are : map, filter, sorted etc, (I only know these as of now).

  - Terminal methods are: reduce, collect, forEach, findFirst etc,

Parallel Streams
Using Parallel streams we can divide the code into multiple streams and make use of the cores of the cpu, each thread runs on separate cores and result is the combination of the execution. Use parallel streams when one don't care about the order of execution. The result is unaffected and the state of one element doesn't affect the other.

> Difference between Arrays.asList() and ArrayList(Arrays.asList())
Arrays.asList()

> This method acts as a bridge between the array based and collection based APIs, it is used to return the fixed size list backed by specific array. We cannot add or remove the elements in the array, we can only modify them and if there were any changes done to the list then the changes will reflect in the original array.

:exclamation: ArrayList(Arrays.asList())
This method is similar to the Arrays.asList() but we can add or remove the elements and modify, but the original array remains untouched.

Functional interfaces:
Interfaces from java8 can have default and static methods with body in interfaces. We can add a default method with an implementation, then why to have static methods, if we want others to add their own implementation then we have to use default method, and if we don't want others to implement and have to use my own implmentation, then we have to use static, because static methods cannot be overriden.

Lambda Expressions
It is feature which allows us to treat actions as objects.
lambda expressions are used to implement a functional interface without implementing a class or an anonymous class, a functional interface is an interface which is having only one abstract method, but can also have any number of default methods.

### Functional programming

- A programming style which treats computation as mathematical evaluation and reduces mutations on data, no iteration, no loops.
- In fuctional programming we just declare what to do, we don't say how to do.
- Fuctional programming doesn't add anything new to java. it just makes the code more readable and maintainable.
- It is a declarative approach, where we declare what to do and thats it. There are many different functional interfaces available.

map() method uses Function interface and return type and parameter of this inteface can be any other datatype which is of wrapper class, filter() method uses predicate interface and return type is boolean, reduce() method is Binary Operator interface, forEach is consumer interface and the return type of this interface is void, sorted uses comparator interface.

**Inner class** a class inside a class. Types of inner class.

1. Member class(non static class)
1. Static class
1. Anonymous class

Inner classes are defined as the class that is declared or defined inside another class, when the purpose of a class is to work with only one class, then declaring it inside makes the code more readable and maintainable, rather than declaring it outside. A inner class can be private and it can access the private members of the outer class as well.

**Wrapper class** provides a way to use primitive data types as objects. Wrapper class comes handy when working with collection frameworks where primitive data types cannot be used.

- Putting a primitive value inside an object is known as boxing.
- Getting primitive value from an object is known as unboxing.

### Layered Architecture

- Data Access layer provides interface between business logic layer and underlying database
- Business layer is used to validate the user credentials.
- Presentation layer is responsible for exception handling.
- DTO (Data Transfer Object) is used to encapuslate business data
- Service layer is responsible for implementing business rules and policies.
- Presentation layer or the UI is the combination of all other layers.

## Regular Expressions

``` re

find -->search for the find returns boolean

start-->start index of the match

end --->end index of the match end+1 index ..

group -->matched one will return

character classes:

[abc]-->either a or b or c

[^abc]-- other than a or b or c

[a-z]-->any lower case alphabet symbol

[A-Z]-->any upper case alphabet symbol

[a-zA-Z]-->any alphabet symbol

[0-9]-->any digit from 0-9

[a-zA-z0-9]-->any alpha numeric character

[^a-zA-z0-9]-->except alpha numeric character(special symbols)

pre defined char classes:
=========================== compiler will treat \ as escape char so we have to use \\s

\s-->search for space char..

\S-->except space char

\d -->any digit from 0-9

\D-->except digits any char

\w-->any word char(alpha numeric)

\W-->except word char (special symbols)

.-->any char

Quantifiers:
------------- tospecify number of occurences

a exactly one a

a+ atleast one a

a* any number of a's including zero number also

a? atmost one a
```
