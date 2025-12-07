
## **Previously Asked Questions for OOPS (SE,IT and COE/CSE) - ENHANCED VERSION 2**

| **Section** | **Unit** | **Topic Areas** |
| :--- | :--- | :--- |
| **PART 1** | **Unit 1** | [OOP Paradigm, Classes, Static/Friend Members, Constructors](#unit-1-object-oriented-paradigm--c-at-a-glance) |
| **( asked in** | **Unit 2** | [Dynamic Objects (new/delete), Operator Overloading, Virtual Functions, Templates](#unit-2-dynamic-objects-operator-overloading--templates) |
| **End-Sem** | **Unit 3** | [Java Basics (JVM/Bytecode), Interfaces, Packages, Vectors](#unit-3-java-basics--oop-concepts) |
| **⭕𝐑**| **Unit 4** | [Exception Handling (throw/throws), Multithreading (Sync/Lifecycle)](#unit-4-exception-handling--multithreading) |
|**Supp**| **Unit 5** | [File I/O, Serialization, Networking (Sockets)](#unit-5-input-output-file-operations--networking) |
|**papers)**| **Unit 6** | [Applets, Swing GUI, Event Handling](#unit-6-applets-and-java-swing) |
| | | |
| **PART 2** | **Unit 1** | [C++ Concepts (this, namespace), Coding (Swap, Friend Functions)](#part-2-mid-semester-questions-secondary) |
|**(Mid-Sem)**| **Unit 2** | [Dynamic Init, Diamond Problem, Template Overloading](#unit-2-dynamic-objects-operator-overloading--templates-1) |

***

# **PART 1: END-SEMESTER & SUPPLEMENTARY QUESTIONS (Priority)**  
*(From 20+ Full-Syllabus EndTerm Papers: 2025, 2024, 2023, 2022, 2019, 2018)*

## **Unit 1: Object Oriented Paradigm & C++ at a Glance**

### **Object-Oriented Paradigm & C++ Overview**
*    What is abstraction in OOP?
*    Define the term "object" in Object-Oriented Programming.
*    State one difference between structured programming and object-oriented programming.
*    Describe the features that differentiate object-oriented programming languages from structured programming languages which do not support objects. Name a few OOP languages.
*    Differentiate between Object Oriented Programming, Procedure Oriented Programming, and Pure Object Oriented Programming.
*    **[NEW]** Differentiate between Object-oriented approach and Object-based approach. Explain with examples (e.g., JavaScript before ES6).
*    **[NEW]** Differentiate between class and union in C/C++. Give suitable examples, focusing on memory layout, active members, and typical use cases.

### **Classes and Objects (Constructors, Static, Friend, Nested)**
*    What do you mean by static data members?
*    Differentiate between shallow copy and deep copy.
*    What is the purpose of a constructor in C++?
*    Illustrate the use of static data members in a C++ class with an example.
*    Create a program in C++ to demonstrate the use of friend functions and their applications.
*    What is an explicit call and implicit call of a copy constructor?
*    Compare normal function, inline function, macros in C++. Discuss memory usage, advantages, disadvantages.
*    Friend function vs member function (Short Note).
*    What is the role of a nested class? How to use it?
*    Write a program to show the role of `this` keyword in C++.
*    Explain the use of `this` keyword.
*    Implement the following using friend concept: Class `IT_student` and class `mechanical_student`. Use a friend function to add marks of both students.
*    What are the key features of a Constructor? What are different types of constructors? Give an example.
*    **[NEW]** Differentiate between constant pointer and pointer to constant. Give examples: `const int* ptr` vs `int* const ptr` vs `const int* const ptr`.
*    **[NEW]** Write a program for class MATRIX to perform determinant and transpose operations using appropriate member functions.
*    **[NEW]** Create an election voting program using arrays to store candidate names and vote counts. Implement add vote, display results, and find winner.
*    **[NEW]** Design a shopping list program with operations: add item, delete item, display list, and calculate total cost.
*    **[NEW]** Explain the stack mechanism for function calls. How are parameters, local variables, and return addresses stored in stack frames (activation records)?
*    **[NEW]** Write a C++ program to track the number of objects created, destroyed, and currently active using static data members and appropriate constructors/destructors.
*    **[NEW]** When and why would you use a private constructor? Explain with examples (Singleton pattern, Factory pattern).
*    **[NEW]** Differentiate between `new operator` and `operator new`. Explain their syntax, purpose, and when each is used.
*    **[NEW]** Explain the concept of mutual friend classes. Write a program where class A is friend of class B and class B is friend of class A (bidirectional friendship).
*    **[NEW]** Describe the mechanism of accessing data members and member functions in the following cases: (a) inside `main`, (b) inside a member function of the same class, (c) inside a member function of another class.
*    **[NEW]** Design a class `TravelPlan` with data members `PlanCode`, `Place`, `NumberOfTravellers`, `NumberOfBuses`. Provide a constructor with default values (e.g., `PlanCode = 1001`, `Place = "Agra"`, `NumberOfTravellers = 5`, `NumberOfBuses = 1`). Implement `NewPlan()` to input details and set `NumberOfBuses` based on traveller count (<20 →1, 20–39 →2, ≥40 →3) and `ShowPlan()` to display all details.
*    **[NEW]** Define a class `MetroTrain` with data members such as `TrainNo`, `TrainName`, `Source`, `Destination`, `JourneyDateTime`, and `Capacity`. Write member functions to initialize, input, and display the details, and a main program to test the class.
*    **[ENHANCE]** What is a namespace in C++? Explain with detailed examples including: defining namespace, using directive, scope resolution, and avoiding name conflicts.
*    **[ENHANCE]** Explain: Array of pointers vs Pointer to array with complete syntax and memory diagrams.
*    **[ENHANCE]** What are the rules for naming identifiers in C++? List all restrictions and conventions.
*    **[ENHANCE]** List all C++ keywords (total count). Explain 5 keywords not in C: `virtual`, `friend`, `template`, `namespace`, `explicit`.
*    **[ENHANCE]** Are friend functions a threat to data hiding? Discuss with advantages and disadvantages.
*    **[ENHANCE]** Explain object return from functions. What is RVO (Return Value Optimization)? When does it occur?
*    **[ENHANCE]** Define and differentiate: Tokens, Keywords, Constants, Identifiers in C++.
*    **[ENHANCE]** Explain variable scope (global, local, block) and lifetime (static, automatic, dynamic) with examples.
*    **[ENHANCE]** Explain situations where inline expansion may not work: loops, recursion, switch statements, function pointers.
*    **[ENHANCE]** Can destructors be overloaded? Why or why not? (Answer: No, destructors cannot have parameters)
*    **[ENHANCE]** What is a local class in C++? Where can it be defined and what are its limitations?
*    **[ENHANCE]** How is memory allocated to class members? Explain object memory layout, vtable, and static members.
*    **[ENHANCE]** Can a destructor be called explicitly? Explain with example: `obj.~ClassName();` and when this is useful.
*    **[ENHANCE]** Differentiate between: (a) Member function as friend vs (b) General function as friend. Show declaration differences.
*    **[ENHANCE]** Are member functions defined inside the class inline by default? TRUE or FALSE. Explain compiler behavior.

***

## **Unit 2: Dynamic Objects, Operator Overloading & Templates**

### **Dynamic Objects**
*    Using `new` and `delete` operators, show dynamic allocation and deallocation in a C++ code.
*    Create a class `Student` that overloads the `new` and `delete` operators to track memory allocation and deallocation.
*    What is the difference between `delete` and `delete []`?
*    Write a code to implement overloading `new` operator.
*    C++ provides operators to access data members/functions by using pointers (`.*`, `->*`). Explain with code.
*    **[NEW]** Explain pointer to members (`.*` and `->*`) with a detailed example showing pointer to data member and pointer to member function.
*    **[ENHANCE]** Differentiate: `delete` vs `delete[]` with memory deallocation details and consequences of mismatched usage.

### **Operator Overloading and Inheritance**
*    Why is private inheritance rarely used?
*    Explain the role of the scope resolution operator `::`.
*    Explain early binding and late binding. How does a virtual function help in late binding?
*    Virtual destructor and virtual functions in C++ (Differentiate).
*    Analyze the use of operator overloading in C++ with an example program.
*    Explain how a pure virtual function is used to create an abstract class in C++.
*    What is an abstract class (in C++)? Explain its role with the help of a complete example.
*    How is run-time polymorphism achieved in C++? Explain with a program.
*    What is the difference between function overloading, function overriding, constructor overloading, and template overloading?
*    Define a class `string`. Overload the operators `+` and `+=` for the class.
*    How are multipath inheritance (Diamond problem) handled? Give suitable example with code.
*    Differentiate between Overloading and Overriding.
*    Differentiate between inheritance and containership.
*    Write a program to show the use of virtual base class.
*    Explain key features of Friend Function. Write a program to add two complex numbers using friend function to overload `+` operator.
*    Differentiate between function overriding and function overloading with example.
*    Explain virtual base class (Short Note).
*    **[NEW]** Explain object-to-object type conversion using TWO methods: (1) Conversion constructor, (2) Type conversion operator. Show complete example converting Polar to Rectangular coordinates.
*    **[NEW]** What are STL Components? Explain in detail: (a) Containers (vector, list, map, set), (b) Iterators (input, output, forward, bidirectional, random access), (c) Algorithms (sort, find, binary_search). Write a program demonstrating all three.
*    **[NEW]** Create a class Rational to perform rational number arithmetic. Overload operators: `+`, `-`, `*`, `/` for fractions. Show addition of 1/2 + 1/3 = 5/6.
*    **[NEW]** Explain class-to-class type conversion using friend function. Convert class Time (hours, minutes) to class Minutes (totalMinutes). Show both constructor and friend function approaches.
*    **[NEW]** Differentiate between Conversion Constructor and Conversion Operator. When should each be used? Show example with implicit vs explicit conversions.
*    **[NEW]** Write a program demonstrating a friend function in one class that is a member function of another class (cross-class friends). Example: `friend_add()` in class A is member of class B.
*    **[NEW]** Implement memory tracking by overloading global `new` and `delete` operators. Track total bytes allocated, deallocated, and current usage.
*    **[NEW]** Write overloaded functions to calculate the perimeter/circumference of square, circle, rectangle, and triangle in a single C++ program using function overloading.
*    **[ENHANCE]** What precautions should be taken during function overloading to avoid ambiguity? Explain with examples of ambiguous overloading.
*    **[ENHANCE]** Explain overloading of I/O operators (`>>` and `<<`) for a class. Why must they be implemented as friend functions?
*    **[ENHANCE]** Explain the concept of initializer list in multilevel inheritance. Show proper order of initialization for base and derived classes.
*    **[ENHANCE]** Explain ambiguity resolution in inheritance beyond diamond problem. Cover: same function name in multiple bases, scope resolution usage.
*    **[EXAMPLE]** Write a program for String class overloading `+` (concatenation) and `+=` (append) operators. Use copy constructor properly.
*    **[EXAMPLE]** Demonstrate virtual base class with hierarchy: X → A → B (multilevel). Show how virtual keyword prevents duplicate copies.
*    **[EXAMPLE]** Create Employee-Faculty hierarchy with proper inheritance. Faculty has salary calculation based on experience.
*    **[EXAMPLE]** Overload operator to check if a number is prime. Example: `if(obj > 17)` checks if 17 is prime.
*    **[EXAMPLE]** Design Employee-Manager relationship using both inheritance and aggregation. Manager contains list of Employees.
*    **[EXAMPLE]** Create Shape hierarchy (Shape → Circle, Rectangle, Triangle) with virtual function `display_area()` for polymorphism.
*    **[EXAMPLE]** Implement matrix addition using operator+ overloading for class Matrix.
*    **[EXAMPLE]** Demonstrate function overloading with area() for: circle (radius), square (side), rectangle (length, width).
*    **[EXAMPLE]** Create Student→Test→Result hierarchy using multilevel inheritance with proper data flow.
*    **[EXAMPLE]** Write a program to calculate square and cube of a number using dynamic binding (virtual functions).
*    **[EXAMPLE]** Design Vehicle hierarchy: Vehicle → TwoWheeler/FourWheeler with appropriate properties.

### **Generic Programming with Templates**
*    Create a template class `Calculator` that performs basic operations like add, subtract, multiply, and divide for `int` and `float` types.
*    Evaluate the advantages and disadvantages of templates in C++ by designing a function template to swap variables.
*    What are templates in C++ and define its types.
*    What is the concept of inheritance of templates? Write a code for inheritance of a template base class and template derived class.
*    Write a function template for finding the minimum value contained in an array. Distinguish between overloaded functions and function templates.
*    Distinguish between the term class template and template class.
*    Explain templates and its types with detailed example.
*    What are Templates? Write a program to create a Class Template and a Friend Template.
*    **[NEW]** Demonstrate template recursion with example. Write a template function to calculate factorial or Fibonacci numbers using recursion.
*    **[NEW]** Write a function template to find the minimum value in an array of any type (int, float, char). Explain template argument deduction.
*    **[NEW]** Explain template inheritance. Create a base class template `Box<T>` and derived class template `ColoredBox<T>` that inherits from it.
*    **[ENHANCE]** Differentiate between "class template" (definition) and "template class" (instantiation). Explain with examples.
*    **[ENHANCE]** Compare: Constructor overloading vs Template overloading. Can they coexist? Show example.
*    **[EXAMPLE]** Create template class Pair<T> with member function `get_min()` to return minimum of three values.
*    **[EXAMPLE]** Write a function template with multiple parameters: template<typename T> T max(T a, int b).
*    **[EXAMPLE]** Implement template function to swap two variables. Show usage with int, float, and string types.

***

## **Unit 3: Java Basics & OOP Concepts**

### **Java Fundamentals**
*    "JVM is critical for Java programs." Justify.
*    JRE vs JDK vs JVM (Differentiate).
*    List two strictly Java-based features.
*    What is bytecode in Java?
*    Mention one benefit of using Java packages.
*    Name two access specifiers in Java.
*    What is the purpose of the following functions: `toString()`, `nextDouble()`, `System.out.println()`, `public static void main(String args[])`.
*    Explain the access specifiers in java with respect to their privileges by giving an example.
*    Differentiate between Java application vs applet.
*    Explain the concept of bytecode in detail with life stages of a java code.
*    **[ENHANCE]** Explain Java bytecode in detail. Cover: compilation process, bytecode structure, why platform-independent, security benefits, JIT compilation.

### **Designing Classes, Inheritance, & Polymorphism**
*    How does Java support multiple inheritance? Explain in detail with complete code.
*    Interface in JAVA and abstract class in C++ (Differentiate).
*    Package in JAVA and namespace in C++ (Differentiate).
*    Default in JAVA vs private in JAVA (Differentiate).
*    Investigate how abstract classes are implemented in Java and their role in polymorphism.
*    Write a Java program to demonstrate function overriding.
*    What is an interface? Write a code in Java for defining an interface called `cricket_team`.
*    What is the role of packages in Java? Create a user-defined package.
*    Features of Java (Short Note).
*    Implement scenario using Java: `Exam` (interface), `MidSem` (interface), `EndSem` (interface), `IT_BRANCH` (class).
*    **[ENHANCE]** Explain Java packages in detail with: package creation, package hierarchy, import statements, classpath, user-defined package example.
*    **[ENHANCE]** Explain Java interfaces with complete cricket_team example including: interface definition, implementing classes, multiple interface implementation.
*    **[ENHANCE]** Explain all Java access specifiers with privilege table: public, private, protected, default. Show cross-package access rules.
*    **[ENHANCE]** Explain abstract classes in Java with detailed example. Differentiate from interfaces. When to use which?
*    **[ENHANCE]** Write a comprehensive Java program demonstrating function overriding with @Override annotation, super keyword usage, and polymorphism.
*    **[EXAMPLE]** Create a simple Student class in Java with roll_no and name. Implement methods to accept and display student data.
*    **[EXAMPLE]** Demonstrate type conversion and type casting in Java: primitive types, wrapper classes, upcasting, downcasting.
*    **[EXAMPLE]** Write programs demonstrating: Math class (abs, pow, sqrt), String class (length, substring, concat), Vector class (add, remove), ArrayList class (add, get, size).

### **Additional Topics (Vectors/ArrayList)**
*    Explain the differences between `Vector` and `ArrayList` in terms of memory management, performance, and type safety.
*    Write a Java program to insert, update, iterate and delete the elements in a `Vector`.

***

## **Unit 4: Exception Handling & Multithreading**

### **Exception Handling**
*    How are exceptions handled in C++? How is rethrowing an exception different from a catch-all block? Explain with code.
*    Describe the role of `throw` and `throws` in Java exception handling with examples.
*    What is the difference between checked and unchecked exceptions in Java?
*    Write a program that demonstrates exception handling with nested try-catch, custom exception, and finally block.
*    What is rethrowing an exception? Explain with a C++ example.
*    What is exception, and type of exceptions in C++? Give a code to handle different exceptions. How is it different from if-else?
*    Explain exception handling in C++. How is an exception rethrown? Also explain the concept of multiple catch and catch all.
*    What is the difference between error and exception in Java? How are exceptions handled in Java.
*    What are the different catch blocks? Why and how to rethrow an exception?
*    **[ENHANCE]** Explain checked vs unchecked exceptions in Java with detailed examples: IOException (checked), NullPointerException (unchecked), ArithmeticException (unchecked). Show how checked exceptions must be declared or caught.
*    **[ENHANCE]** Differentiate between `throw` and `throws` in Java: `throw` (inside method body to throw exception), `throws` (in method signature to declare exceptions). Show complete example.
*    **[ENHANCE]** What is exception specification in C++? Explain throw() specification (deprecated in C++11). Show how to restrict exceptions.
*    **[ENHANCE]** Explain rethrowing exceptions in C++ with proper example. Show difference between `throw;` (rethrow) and `throw e;` (new throw).
*    **[EXAMPLE]** Write a program with user-defined exception class in C++. Override `what()` function from std::exception.
*    **[EXAMPLE]** Demonstrate nested try-catch with custom exception and finally block in Java. Show exception propagation.

### **Multithreaded Programming**
*    What is multithreading in JAVA? Implement using any one of the options.
*    Create a multithreading program with two threads (one prints 1-10, another A-J). Use synchronization. Explain thread lifecycle.
*    Write a Java program that demonstrates multithreading with thread synchronization.
*    Explain the states of a thread in detail with a diagram.
*    What are the two ways to implement multithreading in Java?
*    What is multithreading? Show synchronization of threads with the help of code.
*    **[ENHANCE]** Draw and explain complete thread lifecycle diagram in Java: New, Runnable, Running, Blocked/Waiting, Terminated. Show transitions.
*    **[ENHANCE]** Explain the two ways to create threads in Java: (1) Extending Thread class, (2) Implementing Runnable interface. Show complete examples with pros/cons.
*    **[EXAMPLE]** Write a comprehensive multithreading program with synchronization, thread priorities, and proper lifecycle management.

***

## **Unit 5: Input-Output, File Operations & Networking**

### **I/O and File Handling**
*    Write a program in Java that demonstrates serialization to save and retrieve an object's state.
*    Working with data files (Short Note).
*    Analyze how the stack is used to implement function calls (Note: This is technically system/stack concept but appeared here).
*    Illustrate how class objects can be written and read from the files.
*    Explain with an example to open, close, and write data to the file.
*    Write a C++ program to read a file and count the no. of vowels and consonants.
*    **[NEW - CRITICAL]** Explain Java Serialization in detail. Write a complete program demonstrating: (1) Making a class Serializable, (2) Using ObjectOutputStream to save objects, (3) Using ObjectInputStream to retrieve objects, (4) transient keyword usage, (5) serialVersionUID.
*    **[NEW]** What are streams in C++? Explain the concept of input, output, and error streams and describe the predefined streams (such as `cin`, `cout`, `cerr`, `clog`) with typical usage.
*    **[ENHANCE]** Explain console I/O formatting in C++: formatted I/O (setw, setprecision, setfill) vs unformatted I/O (get, put, read, write). Show examples.
*    **[ENHANCE]** Explain two ways to detect EOF (End of File) in C++: (1) using eof() function, (2) using fail() function. Show both methods with file reading example.
*    **[ENHANCE]** Explain how class objects can be serialized (written) and deserialized (read) from files in C++. Show complete example with file handling.
*    **[EXAMPLE]** Write a detailed program demonstrating: opening file, writing data, reading data, checking errors, closing file in C++.

### **Networking Concepts**
*    Explain the client-server model in networking. Provide a simple example of client-server interaction using sockets.
*    Explain with a program how the client-server model is implemented in Java using socket programming.
*    **[EXAMPLE]** Write a complete Java client-server program using sockets. Client sends message, server receives and responds. Show both client and server code.

***

## **Unit 6: Applets and Java Swing**

### **Applets**
*    Create an applet that contains a button and a text field. Implement event handling for the button click.
*    What are applets? Discuss their use.
*    What is java applet? Give its properties. Create a basic applet which will print "Hello User".
*    What are Applets? Write a program in Java to design a simple Applet.
*    Explain Java applets in detail. Create an applet using any 4 functions from `Graphics` class.
*    **[EXAMPLE]** Write a complete applet program with button, text field, and event handling using ActionListener.
*    **[EXAMPLE]** Demonstrate Graphics class functions in applet: drawLine(), drawRect(), drawOval(), fillRect(), setColor().

### **Java GUI Technologies (Swing/Servlets)**
*    Write a Java program to design a GUI-based calculator using Swing, including basic event handling.
*    Explain the differences between Swing and Servlets in Java.
*    **[NEW]** Write a comprehensive Java Swing calculator program with: JFrame, JPanel, JButton, JTextField, ActionListener, event handling for +, -, *, / operations. Include clear and equals functionality.
*    **[ENHANCE]** Differentiate between Swing and Servlets in detail: Swing (GUI, client-side, desktop apps) vs Servlets (server-side, web apps, HTTP). Show use cases.

***

# **PART 2: MID-SEMESTER QUESTIONS (Secondary)**  
*(From 15+ Partial-Syllabus MidTerm Papers: Focused on Units 1 & 2 mainly)*

## **Unit 1: Object Oriented Paradigm & C++ at a Glance**

### **Concepts & Differences**
*   **[2025 Mid]** Method overloading is different from method overriding. Explain.
*   **[2025 Mid]** Can destructors be overloaded? Why or why not?
*   **[2025 Mid]** Why can't we have 'this' pointer with static members?
*   **[2024 Mid]** Differentiate between Object-oriented vs procedure-oriented programming.
*   **[2023 Mid]** Difference: `class variable` vs `static member function`.
*   **[2022 Mid]** Difference between object oriented, object based and pure object oriented languages.
*   **[2019 Mid]** Differentiate Call by value vs call by reference using 'object as argument' concept.
*   **[2018 Mid]** What is a namespace?
*   **[2014 Mid]** How does `main()` function in C++ differ from `main()` in C? Need of `<iostream>`.
*   **[2013 Mid]** Are member functions defined inside class inline by default? TRUE or FALSE.

### **Coding & Implementation**
*   **[2025 Mid]** Write code so `S1++` and `++S1` can coexist (Operator Overloading pre/post).
*   **[2024 Mid]** Write a C++ program using reference variables to swap values.
*   **[2024 Mid]** Define a class `Bank Account` (Initialize, Deposit, Withdraw).
*   **[2023 Mid]** Friend function to print sum of digits/reverse (Menu driven).
*   **[2018 Mid]** Parameterized constructor for class `distance` (feet, inches) with default values.
*   **[2010 Mid]** Class `time` (hr, min, sec). Add two time objects.
*   **[EXAMPLE]** Write program for Distance class (feet, inches) with parameterized constructor having default values.
*   **[EXAMPLE]** Create Time class with member functions to add two time objects and display in HH:MM:SS format.

***

## **Unit 2: Dynamic Objects, Operator Overloading & Templates**

### **Dynamic Objects & Pointers**
*   **[2025 Mid]** How is copy constructor used? Explain w.r.t the syntax used.
*   **[2023 Mid]** What are `void*` and `size_t`?
*   **[2023 Mid]** Differentiate `new operator` and `operator new`.
*   **[2022 Mid]** What do you mean by dynamic initialization of a variable?
*   **[2018 Mid]** What are `new` and `delete` in C++? Purpose and syntax.

### **Inheritance & Polymorphism**
*   **[2025 Mid]** What is diamond shaped class inheritance problem and how is it solved?
*   **[2025 Mid]** Show the use of initializer list in inheritance using a complete C++ code.
*   **[2024 Mid]** What is the purpose of pure virtual function? How is it different from virtual function?
*   **[2024 Mid]** Differentiate Dynamic binding vs Static Binding.
*   **[2022 Mid]** Steps to invoke suitable function if function overloading is done.
*   **[2019 Mid]** What is the role of `::` in inheritance?
*   **[2019 Mid]** Write a program to show the use of virtual base class.
*   **[EXAMPLE]** Demonstrate STRING class with operator+ that uses copy constructor for concatenation: `string s3 = s1 + s2;`

### **Templates**
*   **[2025 Mid]** Where can we use templates in coding? Function templates can be overloaded too - justify.
*   **[2024 Mid]** Create a derived class template `ColoredBox<T>` that inherits from `Box<T>`.
*   **[2018 Mid]** Write a function template `max(T, int)` to return max of two numbers.
