What is JVM?
Java  Virtual Machine is a process  virtual machine that performs on bytecode. Every java program generates a class file called bytecode after compilation. It is designed in a way that it can allow the programs built could be run on any platform and without any modification or recompilation. JVM makes it possible because it knows the underlying hardware.

What is JDK and JRE?
Java Development Kit is a full featured software development kit which provides development tools as well as JRE , a compiler, a debugger  which are used to develop ,compile and execute an application .

JRE is Java Runtime Environment which is basically a virtual machine, it provides the minimum requirements for  a  java program to execute.

What is relationship between a class and an object?
A class is a user-defined blueprint or prototype, where we can create objects which are having common set of properties. An object is an instance of a class and have some state and behaviour, where state is defined as attributes and behaviour is defined as functions or methods. Consider a class called vehicle and we can create any number of objects to the class such as truck,auto etc. 
The new operator is used to create an object and whenever an object is created the class is said to be instantiated, and memory is allocated for  every field which is defined in the class.
	
What is an object?
A group of related variables and functions that are combined as a single unit is called objects

What is the difference between sleep() and wait() ?
The sleep method blocks the thread from performing and holding the lock on shared object for specified amount of  time.
Where as the wait method just pauses the thread until a notification is received from other thread without  holding the lock on the shared object.

Is Java pass by value or pass by reference?
Java is always pass by value, when we pass the value of an object, we are passing the reference to it.


What is difference between fail-fast and fail-safe?


The Iterator's fail-safe property works with the clone of the underlying collection and thus, it is not affected by any modification in the collection. All the collection classes in java.util package are fail-fast, while the collection classes in java.util.concurrent are fail-safe. Fail-fast iterators throw a ConcurrentModificationException, while fail-safe iterator never throws such an exception.


Statements about static keyword
We can have static  block in a class and can have static method implementations in interface 

Statements about jdk,jvm,jre
JVM is responsible for converting the bytecode to machine specific-code. We only need JRE to run the program, JDK compiles the code.

Can we have two main methods?
Yes, we can. By method overloading.

Strings
String a ="abc";
String b =  new String("abcd");
total 3 objects are created in this example, The first line is object in string pool and the second line's abcd will be first created as an object and then passed to the heap memory because of the new keyword.

why can't we declare a top level class as static?
Top level classes are by default static classes, so there is no point of declaring a class as static. If there is a non-static inner class  it cannot exist without the instance of the outer class.

Why can't we have a top level class as private?
Top level classes cannot be declared as private, because private classes cannot be accessed from the outside, if we declare JVM cannot access the main method in the top level class,  so this is the reason we get compilation error, if we declare a top level class private.

Why and How java is platform Independent?
Compiler vs Interpreter
Compiler  generates machine code, it will translate only once, compiled programs can run independently, this is fast
Interpreter translate every time we run the code and it does not generate any machine code file, interpreted programs always need interpreter

Java code generates bytecode which is class file,  compiler checks the source code for errors and generates a error free bytecode, which runs on JVM, JVM converts bytecode to machine code, it is an interpreter.