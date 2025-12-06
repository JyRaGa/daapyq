## **Previously Asked Questions for OOPS (SE,IT and COE/CSE)**

| **Section** | **Unit** | **Topic Areas** |
| :--- | :--- | :--- |
| **PART 1** | **Unit 1** | [OOP Paradigm, Classes, Static/Friend Members, Constructors](#unit-1-object-oriented-paradigm--c-at-a-glance) |
| *(from End-Sem Papers)* | **Unit 2** | [Dynamic Objects (new/delete), Operator Overloading, Virtual Functions, Templates](#unit-2-dynamic-objects-operator-overloading--templates) |
| | **Unit 3** | [Java Basics (JVM/Bytecode), Interfaces, Packages, Vectors](#unit-3-java-basics--oop-concepts) |
| | **Unit 4** | [Exception Handling (throw/throws), Multithreading (Sync/Lifecycle)](#unit-4-exception-handling--multithreading) |
| | **Unit 5** | [File I/O, Serialization, Networking (Sockets)](#unit-5-input-output-file-operations--networking) |
| | **Unit 6** | [Applets, Swing GUI, Event Handling](#unit-6-applets-and-java-swing) |
| | | |
| **PART 2 (Mid-Sem)** | **Unit 1** | [C++ Concepts (this, namespace), Coding (Swap, Friend Functions)](#part-2-mid-semester-questions-secondary) |
|| **Unit 2** | [Dynamic Init, Diamond Problem, Template Overloading](#unit-2-dynamic-objects-operator-overloading--templates-1) |

# **PART 1: END-SEMESTER & SUPPLEMENTARY QUESTIONS (Priority)**
*(From 20+ Full-Syllabus EndTerm Papers: 2025, 2024, 2023, 2022, 2019, 2018)*

## **Unit 1: Object Oriented Paradigm & C++ at a Glance**

### **Object-Oriented Paradigm & C++ Overview**
*    What is abstraction in OOP?
*    Define the term "object" in Object-Oriented Programming.
*    State one difference between structured programming and object-oriented programming.
*    Describe the features that differentiate object-oriented programming languages from structured programming languages which do not support objects. Name a few OOP languages.
*    Differentiate between Object Oriented Programming, Procedure Oriented Programming, and Pure Object Oriented Programming.

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

***

## **Unit 2: Dynamic Objects, Operator Overloading & Templates**

### **Dynamic Objects**
*    Using `new` and `delete` operators, show dynamic allocation and deallocation in a C++ code.
*    Create a class `Student` that overloads the `new` and `delete` operators to track memory allocation and deallocation.
*    What is the difference between `delete` and `delete []`?
*    Write a code to implement overloading `new` operator.
*    C++ provides operators to access data members/functions by using pointers (`.*`, `->*`). Explain with code.

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

### **Generic Programming with Templates**
*    Create a template class `Calculator` that performs basic operations like add, subtract, multiply, and divide for `int` and `float` types.
*    Evaluate the advantages and disadvantages of templates in C++ by designing a function template to swap variables.
*    What are templates in C++ and define its types.
*    What is the concept of inheritance of templates? Write a code for inheritance of a template base class and template derived class.
*    Write a function template for finding the minimum value contained in an array. Distinguish between overloaded functions and function templates.
*    Distinguish between the term class template and template class.
*    Explain templates and its types with detailed example.
*    What are Templates? Write a program to create a Class Template and a Friend Template.

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

### **Multithreaded Programming**
*    What is multithreading in JAVA? Implement using any one of the options.
*    Create a multithreading program with two threads (one prints 1-10, another A-J). Use synchronization. Explain thread lifecycle.
*    Write a Java program that demonstrates multithreading with thread synchronization.
*    Explain the states of a thread in detail with a diagram.
*    What are the two ways to implement multithreading in Java?
*    What is multithreading? Show synchronization of threads with the help of code.

***

## **Unit 5: Input-Output, File Operations & Networking**

### **I/O and File Handling**
*    Write a program in Java that demonstrates serialization to save and retrieve an object's state.
*    Working with data files (Short Note).
*    Analyze how the stack is used to implement function calls (Note: This is technically system/stack concept but appeared here).
*    Illustrate how class objects can be written and read from the files.
*    Explain with an example to open, close, and write data to the file.
*    Write a C++ program to read a file and count the no. of vowels and consonants.

### **Networking Concepts**
*    Explain the client-server model in networking. Provide a simple example of client-server interaction using sockets.
*    Explain with a program how the client-server model is implemented in Java using socket programming.

***

## **Unit 6: Applets and Java Swing**

### **Applets**
*    Create an applet that contains a button and a text field. Implement event handling for the button click.
*    What are applets? Discuss their use.
*    What is java applet? Give its properties. Create a basic applet which will print "Hello User".
*    What are Applets? Write a program in Java to design a simple Applet.
*    Explain Java applets in detail. Create an applet using any 4 functions from `Graphics` class.

### **Java GUI Technologies (Swing/Servlets)**
*    Write a Java program to design a GUI-based calculator using Swing, including basic event handling.
*    Explain the differences between Swing and Servlets in Java.

***
---

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

### **Coding & Implementation**
*   **[2025 Mid]** Write code so `S1++` and `++S1` can coexist (Operator Overloading pre/post).
*   **[2024 Mid]** Write a C++ program using reference variables to swap values.
*   **[2024 Mid]** Define a class `Bank Account` (Initialize, Deposit, Withdraw).
*   **[2023 Mid]** Friend function to print sum of digits/reverse (Menu driven).
*   **[2018 Mid]** Parameterized constructor for class `distance` (feet, inches) with default values.
*   **[2010 Mid]** Class `time` (hr, min, sec). Add two time objects.

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

### **Templates**
*   **[2025 Mid]** Where can we use templates in coding? Function templates can be overloaded too - justify.
*   **[2024 Mid]** Create a derived class template `ColoredBox<T>` that inherits from `Box<T>`.
*   **[2018 Mid]** Write a function template `max(T, int)` to return max of two numbers.
