# **PART 1: UNIT 1 SOLUTIONS**
## **Object Oriented Paradigm & C++ at a Glance**

### **1. Object-Oriented Paradigm & C++ Overview**

#### **Q: What is abstraction in OOP?**
**Answer:**
*   **Definition:** Abstraction refers to the act of representing essential features without including the background details or explanations.
*   **Key Concept:** In OOP, classes use abstraction to define a list of abstract attributes (data) and functions to operate on these attributes, hiding the internal implementation from the user. It is closely related to **encapsulation**.
*   **Balagurusamy Context:** He often describes it as managing complexity by focusing on the "what" rather than the "how".
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    class Car {
    private:
        // Internal details hidden from the user (Abstraction)
        int engineTemp;
        void injectFuel() { /* complex logic */ }

    public:
        // Essential interface exposed to the user
        void start() {
            engineTemp = 0;
            injectFuel();
            cout << "Car started." << endl;
        }
    };

    int main() {
        Car myCar;
        myCar.start(); // User only knows 'start', not 'injectFuel'
        return 0;
    }
    ```

#### **Q: Define the term "object" in Object-Oriented Programming.**
**Answer:**
*   **Definition:** An object is a basic run-time entity in an object-oriented system. It may represent a person, a place, a bank account, or any item that the program has to handle.
*   **Memory:** When a program is executed, the objects interact by sending messages to one another. Objects take up space in memory and have an associated address.
*   **Code Example:**
    ```cpp
    class Student {
        char name;
        int age;
    };
    // In main():
    Student s1; // 's1' is an OBJECT (an instance of class Student) [web:7]
    ```

#### **Q: State one difference between structured programming and object-oriented programming.**
**Answer:**
*   **Structured (POP):** Follows a **Top-Down** approach. The focus is on functions (algorithms) rather than data. Data moves freely around the system.
*   **OOP:** Follows a **Bottom-Up** approach. The focus is on data. Data is hidden and cannot be accessed by external functions (Data Hiding).
*   **Code Example (Conceptual):**
    ```cpp
    // POP Style (Data is global/insecure)
    int count = 0;
    void increment() { count++; }

    // OOP Style (Data is protected)
    class Counter {
        int count; // Private by default
    public:
        void increment() { count++; }
    };
    ```

#### **Q: Differentiate between Object-oriented approach and Object-based approach. Explain with examples.**
**Answer:**
*   **Object-Oriented Programming (OOP):** Supports all three pillars: **Encapsulation**, **Inheritance**, and **Polymorphism**.
    *   *Examples:* C++, Java, C#.
*   **Object-Based Programming:** Supports **Encapsulation** and **Object Identity** (classes/objects), but **DOES NOT** support **Inheritance** or **Polymorphism** (dynamic binding).
    *   *Examples:* JavaScript (pre-ES6), Visual Basic (early versions), Ada.
*   **Code Example (Hypothetical JS difference):**
    ```cpp
    // Object-Based (No inheritance)
    class Box {
       int width;
    };
    // Cannot do: class ColoredBox : public Box { ... }
    ```

#### **Q: Differentiate between class and union in C/C++.**
**Answer:**
*   **Memory:** In a `class` (or `struct`), each member has its own storage location. Total size ≥ sum of sizes of members. In a `union`, all members share the **same** memory location. Size = size of the largest member.
*   **Active Member:** In a `union`, only one member can be active (hold a valid value) at a time.
*   **Use Case:** Classes are for modeling objects. Unions are for memory saving or type punning.
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    union Data {
        int i;
        float f;
    };

    class Student {
        int id;
        float marks;
    };

    int main() {
        cout << "Size of Union: " << sizeof(Data) << endl;   // 4 bytes (max of int/float)
        cout << "Size of Class: " << sizeof(Student) << endl;// 8 bytes (int + float)
        return 0;
    }
    ```

***

### **2. Classes and Objects (Constructors, Static, Friend, Nested)**

#### **Q: What do you mean by static data members? Illustrate with an example.**
**Answer:**
*   **Definition:** A data member declared as `static` is shared by all objects of the class. There is only one copy of the static member in memory, created when the class is loaded.
*   **Initialization:** It must be defined outside the class using the scope resolution operator `::`. Default value is 0.
*   **Visibility:** It is visible only within the class, but its lifetime is the entire program.
*   **Code Example (Tracking Object Count):**
    ```cpp
    #include <iostream>
    using namespace std;

    class Item {
        static int count; // Declaration
        int number;
    public:
        void getdata(int a) {
            number = a;
            count++;
        }
        void getcount() {
            cout << "Count: " << count << endl;
        }
    };

    // Definition of static data member
    int Item::count = 0;

    int main() {
        Item a, b;
        a.getcount(); // 0
        a.getdata(100);
        b.getdata(200);
        b.getcount(); // 2 (Shared variable)
        return 0;
    }
    ```

#### **Q: Differentiate between shallow copy and deep copy.**
**Answer:**
*   **Shallow Copy:** Copies member values bit-by-bit. If a member is a pointer, it copies the address, not the data pointed to. Both objects end up pointing to the same memory location. (Default Copy Constructor).
*   **Deep Copy:** Allocates new memory for the pointer members and copies the *content* into the new memory. Each object has its own separate copy of the data.
*   **Code Example:**
    ```cpp
    class Shallow {
        int* data;
    public:
        Shallow(int d) { data = new int(d); }
        // Default copy constructor does Shallow copy
        // ~Shallow() { delete data; } // Double free error if shallow copy used!
    };

    class Deep {
        int* data;
    public:
        Deep(int d) { data = new int(d); }
        // User-defined Copy Constructor for Deep Copy
        Deep(const Deep &source) {
            data = new int(*source.data); // Allocate NEW memory
        }
    };
    ```

#### **Q: Create a program in C++ to demonstrate the use of friend functions and their applications.**
**Answer:**
*   **Concept:** A `friend` function is a non-member function that has the right to access private and protected members of the class. It is declared inside the class with the `friend` keyword.
*   **Application:** Used for operator overloading and bridging two different classes.
*   **Code Example (Two Classes):**
    ```cpp
    #include <iostream>
    using namespace std;

    class B; // Forward declaration

    class A {
        int x;
    public:
        void setValue(int i) { x = i; }
        friend void add(A, B); // Friend declaration
    };

    class B {
        int y;
    public:
        void setValue(int i) { y = i; }
        friend void add(A, B); // Friend declaration
    };

    void add(A obj1, B obj2) {
        // Accessing private members x and y
        cout << "Sum: " << obj1.x + obj2.y << endl;
    }

    int main() {
        A a; B b;
        a.setValue(10);
        b.setValue(20);
        add(a, b); // Output: Sum: 30
        return 0;
    }
    ```

#### **Q: Differentiate between constant pointer and pointer to constant.**
**Answer:**
*   **Pointer to Constant (`const int* p`):** You cannot change the *value* pointed to, but you can change where the pointer points.
*   **Constant Pointer (`int* const p`):** You cannot change where the pointer *points* (the address), but you can change the value at that address.
*   **Constant Pointer to Constant (`const int* const p`):** Neither the address nor the value can be changed.
*   **Code Example:**
    ```cpp
    int x = 10;
    int y = 20;

    const int* ptr1 = &x; // Pointer to Constant
    // *ptr1 = 15; // ERROR
    ptr1 = &y;     // OK

    int* const ptr2 = &x; // Constant Pointer
    *ptr2 = 15;    // OK
    // ptr2 = &y;  // ERROR
    ```

#### **Q: Write a program for class MATRIX to perform determinant and transpose operations.**
**Answer:**
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    class Matrix {
        int m;
    public:
        void read() {
            cout << "Enter 2x2 matrix elements:\n";
            for(int i=0; i<2; i++)
                for(int j=0; j<2; j++)
                    cin >> m[i][j];
        }
        void transpose() {
            cout << "Transpose:\n";
            for(int i=0; i<2; i++) {
                for(int j=0; j<2; j++)
                    cout << m[j][i] << " ";
                cout << "\n";
            }
        }
        void determinant() {
            int det = (m[0][0] * m) - (m[0] * m[0]);
            cout << "Determinant: " << det << endl;
        }
    };

    int main() {
        Matrix mat;
        mat.read();
        mat.transpose();
        mat.determinant();
        return 0;
    }
    ```

#### **Q: Election contested by five candidates... spoilt ballots.**
**Answer:**
*   **Logic:** Use an array `count` (indices 1-5 for candidates, ignore 0) and a separate variable for spoilt ballots.
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    int main() {
        int count = {0}; // To store votes for candidates 1-5
        int spoilt_ballots = 0;
        int vote;
        int n;

        cout << "Enter number of voters: ";
        cin >> n;

        cout << "Enter votes (1-5): \n";
        for(int i=0; i<n; i++) {
            cin >> vote;
            if(vote >= 1 && vote <= 5) {
                count[vote]++;
            } else {
                spoilt_ballots++;
            }
        }

        for(int k=1; k<=5; k++) {
            cout << "Candidate " << k << ": " << count[k] << " votes\n";
        }
        cout << "Spoilt Ballots: " << spoilt_ballots << endl;
        return 0;
    }
    ```

#### **Q: Design a shopping list program using a class ITEMS...**
**Answer:**
*   **Design:** Use arrays to store codes and prices. `delete` is logical (shifting elements), not memory `delete`.
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    const int m = 50; // Max items

    class ITEMS {
        int itemCode[m];
        float itemPrice[m];
        int count;
    public:
        ITEMS() { count = 0; } // Constructor
        void addItem(int code, float price) {
            itemCode[count] = code;
            itemPrice[count] = price;
            count++;
        }
        void deleteItem(int code) {
            for(int i=0; i<count; i++) {
                if(itemCode[i] == code) {
                    itemPrice[i] = 0; // Logically remove price
                    // Usually we shift elements, but simple zeroing shown for brevity
                    itemCode[i] = 0;
                }
            }
        }
        void displayTotal() {
            float sum = 0;
            for(int i=0; i<count; i++) sum += itemPrice[i];
            cout << "Total Value: " << sum << endl;
        }
    };

    int main() {
        ITEMS order;
        order.addItem(101, 50.5);
        order.addItem(102, 20.0);
        order.displayTotal(); // 70.5
        order.deleteItem(102);
        order.displayTotal(); // 50.5
        return 0;
    }
    ```

#### **Q: Explain the stack mechanism for function calls (Activation Records).**
**Answer:**
*   **Concept:** When a function is called, a block of memory called a "Stack Frame" or "Activation Record" is pushed onto the call stack.
*   **Contents of Frame:**
    1.  **Return Address:** Where to go back after function ends.
    2.  **Parameters:** Arguments passed to the function.
    3.  **Local Variables:** Variables declared inside the function.
*   **Process:** LIFO (Last In, First Out). When function returns, the frame is popped, and local variables are destroyed.
*   **Code Example:**
    ```cpp
    void funcB() {
        int b = 20; // Stored in funcB's stack frame
    } // Frame popped here

    void funcA() {
        int a = 10; // Stored in funcA's stack frame
        funcB();    // funcB frame pushed on top of funcA frame
    }
    ```

#### **Q: When and why would you use a private constructor?**
**Answer:**
*   **Purpose:** To prevent the instantiation of a class from outside.
*   **Use Cases:**
    1.  **Singleton Pattern:** Ensure only one instance of the class exists.
    2.  **Factory Pattern:** Force object creation through a specific static method.
*   **Code Example (Singleton):**
    ```cpp
    #include <iostream>
    using namespace std;

    class Singleton {
    private:
        static Singleton* instance;
        // Private Constructor
        Singleton() { cout << "Instance Created\n"; }
    public:
        static Singleton* getInstance() {
            if (!instance)
                instance = new Singleton();
            return instance;
        }
    };

    Singleton* Singleton::instance = 0;

    int main() {
        // Singleton s; // ERROR: Private Constructor
        Singleton* s = Singleton::getInstance(); // OK
        return 0;
    }
    ```

#### **Q: Explain Mutual Friend Classes.**
**Answer:**
*   **Definition:** Class A is a friend of Class B, and Class B is a friend of Class A. This allows them to access each other's private members freely.
*   **Code Example:**
    ```cpp
    class B; // Forward Declaration

    class A {
        int x;
        friend class B; // B can access A's private data
    public:
        A() { x = 10; }
    };

    class B {
        int y;
        friend class A; // A can access B's private data
    public:
        B() { y = 20; }
        void showA(A& a) { cout << "A's x: " << a.x << endl; } // Accessing private x
    };

    int main() {
        A objA;
        B objB;
        objB.showA(objA);
        return 0;
    }
    ```

#### **Q: Design a class `TravelPlan`...**
**Answer:**
*   **Code Example:**
    ```cpp
    #include <iostream>
    #include <string>
    using namespace std;

    class TravelPlan {
        long PlanCode;
        char Place;
        int NumberOfTravellers;
        int NumberOfBuses;

    public:
        TravelPlan() {
            PlanCode = 1001;
            // String copy or manual assignment usually done here
            NumberOfTravellers = 5;
            NumberOfBuses = 1;
        }

        void NewPlan() {
            cout << "Enter Plan Code, Place, Travellers: ";
            cin >> PlanCode >> Place >> NumberOfTravellers;
            if (NumberOfTravellers < 20) NumberOfBuses = 1;
            else if (NumberOfTravellers < 40) NumberOfBuses = 2;
            else NumberOfBuses = 3;
        }

        void ShowPlan() {
            cout << PlanCode << "\t" << Place << "\t" << NumberOfBuses << endl;
        }
    };
    ```

***


# **PART 1: UNIT 2 SOLUTIONS**
## **Dynamic Objects, Operator Overloading & Templates**

### **1. Dynamic Objects**

#### **Q: Using `new` and `delete` operators, show dynamic allocation and deallocation in a C++ code.**
**Answer:**
*   **Concept:** The `new` operator allocates memory from the free store (heap) during runtime. The `delete` operator frees that memory.
*   **Syntax:**
    *   Pointer = `new` Type;
    *   `delete` Pointer;
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    int main() {
        // Allocate single integer
        int *p = new int;
        *p = 25;
        cout << "Value: " << *p << endl;

        // Allocate array
        int *arr = new int;
        arr = 10;

        // Deallocate
        delete p;      // Delete single object
        delete[] arr;  // Delete array
        return 0;
    }
    ```

#### **Q: Create a class `Student` that overloads the `new` and `delete` operators.**
**Answer:**
*   **Purpose:** To control memory allocation for specific objects (e.g., for debugging or custom memory pools). These functions are implicitly `static`.
*   **Code Example:**
    ```cpp
    #include <iostream>
    #include <cstdlib> // for malloc/free
    using namespace std;

    class Student {
        char name;
        int age;
    public:
        // Overloading new
        void* operator new(size_t size) {
            cout << "Custom new operator called. Size: " << size << endl;
            return malloc(size);
        }
        // Overloading delete
        void operator delete(void* p) {
            cout << "Custom delete operator called." << endl;
            free(p);
        }
    };

    int main() {
        Student *s = new Student(); // Calls custom new
        delete s;                   // Calls custom delete
        return 0;
    }
    ```

#### **Q: What is the difference between `delete` and `delete []`?**
**Answer:**
*   **`delete ptr`:**
    *   Used to deallocate memory for a **single object**.
    *   Calls the destructor **once** for the object pointed to.
*   **`delete [] ptr`:**
    *   Used to deallocate memory for an **array of objects**.
    *   Calls the destructor for **every element** in the array (e.g., if array size is 10, destructor is called 10 times).
    *   *Warning:* Using `delete` instead of `delete []` for an array leads to undefined behavior (memory leaks).

#### **Q: C++ provides operators to access data members/functions by using pointers (`.*`, `->*`). Explain with code.**
**Answer:**
*   **Concept:** These are "Pointer-to-Member" operators. They allow you to access a member of a class given a pointer to that member and an object (or pointer to an object).
    *   `.*` : Access member using object instance.
    *   `->*` : Access member using object pointer.
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    class Test {
    public:
        int num;
        void show() { cout << "Num: " << num << endl; }
    };

    int main() {
        Test t;
        Test *ptr = &t;

        // Pointer to data member 'num'
        int Test::* pNum = &Test::num;

        // Pointer to member function 'show'
        void (Test::* pFunc)() = &Test::show;

        t.*pNum = 10;       // Using object (.*)
        (ptr->*pFunc)();    // Using pointer (->*) -> Output: Num: 10
        return 0;
    }
    ```

***

### **2. Operator Overloading and Inheritance**

#### **Q: Why is private inheritance rarely used?**
**Answer:**
*   **Concept:** Private inheritance means "Is-Implemented-In-Terms-Of". It does not establish an "Is-A" relationship (like public inheritance).
*   **Reason:**
    1.  It limits code reusability because derived class objects cannot be treated as base class objects.
    2.  The "Containership" (Composition) approach is preferred for "Has-A" relationships because it is cleaner and allows using multiple instances of the same class.

#### **Q: Explain the role of the scope resolution operator `::`.**
**Answer:**
*   **Roles:**
    1.  **Accessing Global Variables:** When a local variable has the same name as a global one.
    2.  **Defining Member Functions:** Defining class functions outside the class body.
    3.  **Static Members:** Accessing static variables/functions.
    4.  **Inheritance:** resolving ambiguity in multiple inheritance or accessing overridden base class functions.
*   **Code Example:**
    ```cpp
    int x = 10; // Global
    void func() {
        int x = 20; // Local
        cout << ::x; // Prints 10 (Global)
    }
    ```

#### **Q: Explain early binding and late binding. How does a virtual function help in late binding?**
**Answer:**
*   **Early Binding (Static):** The compiler decides which function to call at **compile-time**. Used for normal functions and overloaded functions. fast execution.
*   **Late Binding (Dynamic):** The decision of which function to call is made at **run-time** based on the type of object pointed to.
*   **Virtual Function:** The keyword `virtual` tells the compiler to defer the function call resolution until runtime. It uses a "V-Table" (Virtual Table) to find the correct function for the object.

#### **Q: Virtual destructor and virtual functions in C++ (Differentiate).**
**Answer:**
*   **Virtual Function:** Ensures the correct *derived* class function is called when accessed via a base class pointer. Used for polymorphism.
*   **Virtual Destructor:** Ensures the *derived* class destructor is called when a base class pointer pointing to a derived object is deleted. Without it, only the base destructor runs, causing memory leaks.
*   **Code Example (Destructor):**
    ```cpp
    class Base {
    public:
        virtual ~Base() { cout << "Base Destroyed"; }
    };
    class Derived : public Base {
    public:
        ~Derived() { cout << "Derived Destroyed"; }
    };
    // deleting Base* pointing to Derived will now print "Derived Destroyed" then "Base Destroyed"
    ```

#### **Q: Analyze the use of operator overloading in C++ with an example program.**
**Answer:**
*   **Concept:** Giving special meaning to existing operators (like `+`, `-`, `<<`) to work with user-defined data types.
*   **Rules:** Cannot overload `::`, `.*`, `.`, `?:`.
*   **Code Example (Complex Number Addition):**
    ```cpp
    #include <iostream>
    using namespace std;

    class Complex {
        float real, img;
    public:
        Complex(float r=0, float i=0) : real(r), img(i) {}

        // Overloading '+' operator
        Complex operator+(Complex c) {
            return Complex(real + c.real, img + c.img);
        }
        void display() { cout << real << " + j" << img << endl; }
    };

    int main() {
        Complex c1(2.5, 3.5), c2(1.5, 2.5);
        Complex c3 = c1 + c2; // Calls operator+
        c3.display(); // 4.0 + j6.0
        return 0;
    }
    ```

#### **Q: Explain how a pure virtual function is used to create an abstract class in C++.**
**Answer:**
*   **Pure Virtual Function:** A function with no definition in the base class, declared as `virtual void show() = 0;`.
*   **Abstract Class:** A class containing at least one pure virtual function.
*   **Role:** It cannot be instantiated. It serves as a blueprint (interface) for derived classes, enforcing them to implement specific functions.

#### **Q: How are multipath inheritance (Diamond problem) handled?**
**Answer:**
*   **Problem:** If Class D inherits from B and C, and both B and C inherit from A, then D gets *two* copies of A. This causes ambiguity.
*   **Solution:** Use **Virtual Base Class**.
*   **Code Example:**
    ```cpp
    class A { public: int x; };
    class B : virtual public A { }; // Virtual inheritance
    class C : virtual public A { }; // Virtual inheritance
    class D : public B, public C { };

    int main() {
        D obj;
        obj.x = 10; // Valid only because of 'virtual' (only one copy of x exists)
        return 0;
    }
    ```

#### **Q: Differentiate between inheritance and containership.**
**Answer:**
*   **Inheritance (Is-A):** Class B inherits properties from Class A. Used when B is a specialized version of A. (e.g., Car is a Vehicle).
    *   *Syntax:* `class Car : public Vehicle`
*   **Containership (Has-A):** Class B contains an object of Class A as a data member. Used when B is composed of A. (e.g., Car has an Engine).
    *   *Syntax:* `class Car { Engine e; };`

#### **Q: Write a program to show the use of virtual base class.**
**Answer:**
*   **Scenario:** Student -> Test, Student -> Sports, Result -> (Test, Sports). Result needs to access Student data.
*   **Code:**
    ```cpp
    #include <iostream>
    using namespace std;

    class Student {
    protected: int roll_no;
    public: void set_roll(int n) { roll_no = n; }
    };

    class Test : virtual public Student { // Virtual Base
    protected: float part1, part2;
    public: void set_marks(float m1, float m2) { part1=m1; part2=m2; }
    };

    class Sports : virtual public Student { // Virtual Base
    protected: float score;
    public: void set_score(float s) { score=s; }
    };

    class Result : public Test, public Sports {
        float total;
    public:
        void display() {
            total = part1 + part2 + score;
            cout << "Roll No: " << roll_no << endl; // No ambiguity
            cout << "Total: " << total << endl;
        }
    };
    ```

#### **Q: [NEW] Object-to-object type conversion (Conversion constructor, Type conversion operator).**
**Answer:**
*   **1. Conversion Constructor (Destination Type):** Converts "Other" type to "Class" type. Defined in the destination class.
*   **2. Casting Operator (Source Type):** Converts "Class" type to "Other" type. Defined in the source class.
*   **Code Example (Polar to Rectangle):**
    ```cpp
    class Rectangle {
        float x, y;
    public:
        Rectangle(float a, float b) : x(a), y(b) {}
        void show() { cout << "Rect(" << x << "," << y << ")\n"; }
    };

    class Polar {
        float r, a;
    public:
        Polar(float radius, float angle) : r(radius), a(angle) {}
        // Casting Operator: Converts Polar -> Rectangle
        operator Rectangle() {
            float x = r * cos(a);
            float y = r * sin(a);
            return Rectangle(x, y);
        }
    };
    ```

***

### **3. Generic Programming with Templates**

#### **Q: Create a template class `Calculator`.**
**Answer:**
*   **Concept:** Use `template <class T>` to define generic data types.
*   **Code Example:**
    ```cpp
    template <class T>
    class Calculator {
        T num1, num2;
    public:
        Calculator(T n1, T n2) : num1(n1), num2(n2) {}
        T add() { return num1 + num2; }
        T subtract() { return num1 - num2; }
    };

    int main() {
        Calculator<int> intCalc(10, 20);
        Calculator<float> floatCalc(2.5, 3.5);
        cout << intCalc.add(); // 30
        cout << floatCalc.add(); // 6.0
        return 0;
    }
    ```

#### **Q: What is the concept of inheritance of templates?**
**Answer:**
*   **Concept:** A class template can inherit from another class template. The derived class must pass its template arguments to the base class.
*   **Note:** When accessing members of the templated base class, you must use `this->member` or `Base<T>::member`.
*   **Code Example:**
    ```cpp
    template <class T>
    class Base {
    protected: T val;
    public: Base(T v) : val(v) {}
    };

    template <class T>
    class Derived : public Base<T> {
    public:
        Derived(T v) : Base<T>(v) {}
        void show() {
            // Must use this->val or Base<T>::val
            cout << "Value: " << this->val << endl;
        }
    };
    ```

#### **Q: Write a function template for finding the minimum value contained in an array.**
**Answer:**
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    template <class T>
    T findMin(T arr[], int size) {
        T min = arr;
        for(int i=1; i<size; i++) {
            if(arr[i] < min)
                min = arr[i];
        }
        return min;
    }

    int main() {
        int iArr[] = {5, 2, 8, 1, 9};
        float fArr[] = {2.2, 1.1, 4.4};
        cout << "Min Int: " << findMin(iArr, 5) << endl;   // Output: 1
        cout << "Min Float: " << findMin(fArr, 3) << endl; // Output: 1.1
        return 0;
    }
    ```

#### **Q: Distinguish between overloaded functions and function templates.**
**Answer:**
*   **Overloaded Functions:** Multiple functions with the *same name* but *different parameter lists*. Each function has a separate definition and code body. Used when different logic is needed for different types.
*   **Function Templates:** A single "blueprint" function. The compiler generates the specific version of the function for the data type used. Used when the *same logic* applies to different types.

#### **Q: [NEW] Template recursion.**
**Answer:**
*   **Concept:** Templates can be recursive, often used in metaprogramming (calculating values at compile time).
*   **Code Example (Factorial):**
    ```cpp
    template <int N>
    struct Factorial {
        static const int value = N * Factorial<N-1>::value;
    };

    // Base Case
    template <>
    struct Factorial<0> {
        static const int value = 1;
    };

    int main() {
        cout << "Factorial of 5: " << Factorial<5>::value << endl; // 120
        return 0;
    }
    ```

***


# **PART 1: UNIT 3 SOLUTIONS**
## **Java Basics & OOP Concepts**

### **1. Java Fundamentals**

#### **Q: JRE vs JDK vs JVM (Differentiate).**
**Answer:**
*   **JVM (Java Virtual Machine):** The engine that executes Java bytecode. It is platform-dependent (there are different JVMs for Windows, Mac, Linux) but enables Java's "Write Once, Run Anywhere" capability. It provides the runtime environment but contains no development tools.
*   **JRE (Java Runtime Environment):** Implementation required to *run* Java applications. It consists of the JVM + Core Classes + Supporting Files. It does not contain compilers or debuggers.
    *   *Equation:* `JRE = JVM + Class Libraries`
*   **JDK (Java Development Kit):** The full kit required to *develop* and *run* Java applications. It contains the JRE + Development Tools (like `javac`, `debugger`, `javadoc`).
    *   *Equation:* `JDK = JRE + Development Tools`

#### **Q: What is bytecode in Java?**
**Answer:**
*   **Definition:** Bytecode is a highly optimized set of instructions designed to be executed by the Java Virtual Machine (JVM). It is the intermediate representation of Java code.
*   **Process:**
    1.  Source Code (`.java`) is compiled by `javac`.
    2.  Compiler produces Bytecode (`.class`).
    3.  JVM interprets/compiles (JIT) this bytecode into native Machine Code for the specific OS.
*   **Significance:** It makes Java platform-independent because the same bytecode file can run on any device with a JVM.
*   **Code Example:**
    ```java
    // Source: Hello.java
    // Compiled to: Hello.class (Bytecode - not readable by humans)
    // Executed by: java Hello
    ```

#### **Q: Explain the access specifiers in java with respect to their privileges.**
**Answer:**
*   **Concept:** Access specifiers determine the visibility of classes, variables, and methods.
*   **Privilege Table:**

| Access Specifier | Same Class | Same Package | Subclass (diff package) | World (diff package) |
| :--- | :---: | :---: | :---: | :---: |
| **public** | Yes | Yes | Yes | Yes |
| **protected** | Yes | Yes | Yes | No |
| **default** (no modifier) | Yes | Yes | No | No |
| **private** | Yes | No | No | No |

*   **Code Example:**
    ```java
    package pack1;
    public class A {
        private int x = 10;   // Only inside A
        int y = 20;           // Default: Inside pack1
        protected int z = 30; // Inside pack1 + Subclasses
        public int w = 40;    // Everywhere
    }
    ```

#### **Q: Differentiate between Java application vs applet.**
**Answer:**
*   **Application:**
    *   Stand-alone program running on the computer.
    *   Executed using `java` command.
    *   Has a `main()` method.
    *   Full access to local system resources.
*   **Applet:**
    *   Small program designed to run within a web browser (or Applet Viewer).
    *   Embeds in HTML pages.
    *   No `main()` method (uses lifecycle methods: `init`, `start`, `paint`).
    *   Restricted access (sandbox security) to local system.

#### **Q: "JVM is critical for Java programs." Justify.**
**Answer:**
*   **Justification:** JVM acts as the bridge between the compiled bytecode and the underlying hardware.
    1.  **Platform Independence:** It translates the universal bytecode into specific machine instructions for the host OS.
    2.  **Security:** It verifies bytecode before execution to prevent unsafe operations.
    3.  **Memory Management:** It handles garbage collection automatically, freeing developers from manual memory control.

***

### **2. Designing Classes, Inheritance, & Polymorphism**

#### **Q: How does Java support multiple inheritance? Explain with code.**
**Answer:**
*   **Concept:** Java **does not** support multiple inheritance with classes (to avoid the Diamond Problem). However, it supports multiple inheritance using **Interfaces**.
*   **Mechanism:** A class can `implement` multiple interfaces.
*   **Code Example:**
    ```java
    interface Father {
        void fun();
    }
    interface Mother {
        void fun();
    }
    // Multiple Inheritance via Interfaces
    class Child implements Father, Mother {
        public void fun() {
            System.out.println("Having fun!");
        }
    }
    class Main {
        public static void main(String args[]) {
            Child c = new Child();
            c.fun();
        }
    }
    ```

#### **Q: Interface in JAVA and abstract class in C++ (Differentiate).**
**Answer:**
*   **Abstract Class (C++/Java):**
    *   Can have both abstract (pure virtual) and concrete (defined) methods.
    *   Can have member variables (state).
    *   Used for "Is-A" relationship with shared code.
*   **Interface (Java):**
    *   Traditionally contained *only* abstract methods and `final static` constants (Java 8+ added default/static methods).
    *   Cannot have instance variables (state).
    *   Used for "Can-Do" capability or defining a contract.
    *   Supports multiple inheritance.

#### **Q: Package in JAVA and namespace in C++ (Differentiate).**
**Answer:**
*   **Java Package:**
    *   Used to group related classes and interfaces.
    *   Maps directly to the directory structure of the file system.
    *   Provides access control (default access).
    *   *Syntax:* `package mypack;`
*   **C++ Namespace:**
    *   Used to avoid name collisions.
    *   Logical grouping, not necessarily physical (file system) grouping.
    *   Does not provide access control visibility (public/private).
    *   *Syntax:* `namespace myname { ... }`

#### **Q: What is the role of packages in Java? Create a user-defined package.**
**Answer:**
*   **Role:**
    1.  **Categorization:** Grouping related classes (e.g., `java.io`, `java.net`).
    2.  **Access Protection:** Default access specifier limits visibility to the package.
    3.  **Name Collision Avoidance:** Keeps class names unique across projects.
*   **Code Example:**
    **File: Tools.java**
    ```java
    package mypack; // Declaration
    public class Tools {
        public void sayHello() {
            System.out.println("Hello from Package!");
        }
    }
    ```
    **File: Test.java**
    ```java
    import mypack.Tools; // Import
    class Test {
        public static void main(String args[]) {
            Tools t = new Tools();
            t.sayHello();
        }
    }
    ```

#### **Q: Write a Java program to demonstrate function overriding.**
**Answer:**
*   **Concept:** When a subclass provides a specific implementation of a method that is already provided by its parent class.
*   **Rules:** Same method name, same return type, same parameters. Use `@Override` annotation (good practice).
*   **Code Example:**
    ```java
    class Bank {
        int getRate() { return 0; }
    }
    class SBI extends Bank {
        @Override
        int getRate() { return 8; }
    }
    class ICICI extends Bank {
        @Override
        int getRate() { return 9; }
    }
    class Test {
        public static void main(String args[]) {
            Bank b;
            b = new SBI();
            System.out.println("SBI Rate: " + b.getRate()); // 8 (Runtime Polymorphism)
            b = new ICICI();
            System.out.println("ICICI Rate: " + b.getRate()); // 9
        }
    }
    ```

***

### **3. Additional Topics (Vectors/ArrayList)**

#### **Q: Explain the differences between `Vector` and `ArrayList`.**
**Answer:**
*   **Synchronization:**
    *   `Vector` is **synchronized** (Thread-safe). Methods are slower.
    *   `ArrayList` is **not synchronized** (Not thread-safe). Methods are faster.
*   **Growth:**
    *   `Vector` doubles its size (100% increase) when full.
    *   `ArrayList` increases size by 50% when full.
*   **Traversal:**
    *   `Vector` can use both `Enumeration` and `Iterator`.
    *   `ArrayList` can only use `Iterator`.

#### **Q: Write a Java program to insert, update, iterate and delete elements in a `Vector`.**
**Answer:**
*   **Code Example:**
    ```java
    import java.util.*;

    class VectorDemo {
        public static void main(String args[]) {
            Vector<String> v = new Vector<>();

            // 1. Insert
            v.add("Apple");
            v.add("Banana");
            v.add("Cherry");

            // 2. Update (Set element at index 1)
            v.set(1, "Blueberry");

            // 3. Delete
            v.remove("Apple"); // Remove by object
            v.remove(1);       // Remove by index (Cherry is now at 1)

            // 4. Iterate
            System.out.println("Vector Elements:");
            Iterator<String> it = v.iterator();
            while(it.hasNext()) {
                System.out.println(it.next());
            }
        }
    }
    ```

***


# **PART 1: UNIT 4 SOLUTIONS**
## **Exception Handling & Multithreading**

### **1. Exception Handling (C++ & Java)**

#### **Q: How are exceptions handled in C++? How is rethrowing an exception different from a catch-all block?**
**Answer:**
*   **Concept:** Exception handling allows a program to deal with runtime errors (like division by zero) without crashing. It uses `try`, `throw`, and `catch` blocks.
*   **Catch-All Block:** Uses `catch(...)` to handle *any* type of exception that was not caught by previous specific catch blocks. It is a "generic" handler.
*   **Rethrowing:** Sometimes a catch block cannot handle the exception completely. It performs some action (like logging) and then passes the exception to the next outer `try-catch` block using the `throw;` statement (without arguments).
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    void test(int x) {
        try {
            if (x == 0) throw "Zero Error"; // Throw string
            if (x == 1) throw 100;          // Throw int
        }
        catch (const char* msg) {
            cout << "Caught in test(): " << msg << endl;
            throw; // RETHROW to main()
        }
        catch (...) { // CATCH-ALL
            cout << "Caught generic exception inside test()" << endl;
        }
    }

    int main() {
        try {
            test(0);
        }
        catch (const char* msg) {
            cout << "Caught in main(): " << msg << endl;
        }
        test(1); // Caught by catch-all inside test()
        return 0;
    }
    ```

#### **Q: Describe the role of `throw` and `throws` in Java exception handling with examples.**
**Answer:**
*   **`throw`:**
    *   Used **inside** a method body.
    *   Used to explicitly throw a single exception object.
    *   *Syntax:* `throw new ArithmeticException("Error");`
*   **`throws`:**
    *   Used in the **method signature**.
    *   Declares that this method *might* throw specific exceptions, delegating the responsibility of handling them to the caller.
    *   Necessary for Checked Exceptions.
    *   *Syntax:* `void func() throws IOException, SQLException { ... }`
*   **Code Example:**
    ```java
    import java.io.*;

    class Test {
        // 'throws' declares that this method is unsafe
        static void readFile() throws IOException {
            throw new IOException("File not found"); // 'throw' creates the exception
        }

        public static void main(String args[]) {
            try {
                readFile();
            } catch (IOException e) {
                System.out.println("Handled in main: " + e.getMessage());
            }
        }
    }
    ```

#### **Q: What is the difference between checked and unchecked exceptions in Java?**
**Answer:**
*   **Checked Exceptions:**
    *   Checked by the compiler at **compile-time**.
    *   The programmer **MUST** handle them (using `try-catch`) or declare them (using `throws`).
    *   *Examples:* `IOException`, `SQLException`, `ClassNotFoundException`.
*   **Unchecked Exceptions:**
    *   Occur at **run-time**; compiler ignores them.
    *   Usually result from programming logic errors. Handling is optional (but recommended).
    *   *Examples:* `ArithmeticException`, `NullPointerException`, `ArrayIndexOutOfBoundsException`.

#### **Q: Write a program that demonstrates exception handling with nested try-catch, custom exception, and finally block.**
**Answer:**
*   **Components:**
    1.  **Custom Exception:** Extend `Exception` class.
    2.  **Nested Try:** `try` block inside another `try` block.
    3.  **Finally:** Block that always executes (used for cleanup).
*   **Code Example:**
    ```java
    // Custom Exception
    class MyException extends Exception {
        MyException(String s) { super(s); }
    }

    class Demo {
        public static void main(String args[]) {
            try { // Outer Try
                int a = 10, b = 0;
                try { // Inner Try
                    if(b == 0) throw new MyException("Custom Divide by Zero");
                } catch (MyException e) {
                    System.out.println("Inner Catch: " + e.getMessage());
                    // Exception handled, flow continues
                }

                int c = a / b; // This throws ArithmeticException

            } catch (ArithmeticException e) { // Outer Catch
                System.out.println("Outer Catch: Standard Zero Error");
            } finally {
                System.out.println("Finally Block: Always Executed");
            }
        }
    }
    ```

#### **Q: Write a program with user-defined exception class in C++.**
**Answer:**
*   **Concept:** Inherit from `std::exception` and override the `what()` virtual function.
*   **Code Example:**
    ```cpp
    #include <iostream>
    #include <exception>
    using namespace std;

    class MyCustomError : public exception {
    public:
        const char* what() const throw() { // Override what()
            return "This is a User-Defined Exception!";
        }
    };

    int main() {
        try {
            throw MyCustomError();
        } catch (exception& e) {
            cout << "Caught: " << e.what() << endl;
        }
        return 0;
    }
    ```

***

### **2. Multithreaded Programming (Java)**

#### **Q: Explain the states of a thread in detail with a diagram.**
**Answer:**
*   **Thread Lifecycle States:**
    1.  **New (Born):** Thread object is created (`new Thread()`) but `start()` is not called yet.
    2.  **Runnable (Ready):** `start()` is called. Thread is ready to run and waiting for CPU time.
    3.  **Running:** The CPU is actively executing the code inside `run()`.
    4.  **Blocked/Waiting:** Thread is inactive (waiting for I/O, sleep, or a lock). It moves back to Runnable when the condition is met.
    5.  **Terminated (Dead):** `run()` method completes execution.

*   **Diagram Description (Textual):**
    `New` --(start)--> `Runnable` <--(Scheduler)--> `Running` --(exit)--> `Terminated`
                          ^                       |
                          |__(sleep/wait)_________|
                                `Blocked`

#### **Q: What are the two ways to implement multithreading in Java?**
**Answer:**
*   **Method 1: Extending `Thread` Class**
    *   Good if you want to modify thread behavior.
    *   Limitation: Cannot extend any other class (Java doesn't support multiple class inheritance).
*   **Method 2: Implementing `Runnable` Interface**
    *   Better flexibility (can extend another class).
    *   Separates the task (Runnable) from the runner (Thread).
*   **Code Example (Both Ways):**
    ```java
    // Way 1: Extend Thread
    class ThreadA extends Thread {
        public void run() { System.out.println("Thread A running"); }
    }

    // Way 2: Implement Runnable
    class TaskB implements Runnable {
        public void run() { System.out.println("Task B running"); }
    }

    class Main {
        public static void main(String args[]) {
            ThreadA t1 = new ThreadA();
            t1.start(); // Starts Thread A

            TaskB task = new TaskB();
            Thread t2 = new Thread(task); // Pass Runnable to Thread
            t2.start(); // Starts Thread B
        }
    }
    ```

#### **Q: Create a multithreading program with synchronization. Explain thread lifecycle.**
**Answer:**
*   **Synchronization:** Used to control access to a shared resource so that only one thread accesses it at a time. Prevents data inconsistency.
*   **Keyword:** `synchronized` method or block.
*   **Code Example:**
    ```java
    class Printer {
        // Synchronized method ensures only one thread enters at a time
        synchronized void printTable(int n) {
            System.out.println("Table of " + n);
            for(int i=1; i<=3; i++) {
                System.out.println(n * i);
                try { Thread.sleep(400); } catch(Exception e){}
            }
        }
    }

    class MyThread extends Thread {
        Printer p; int n;
        MyThread(Printer p, int n) { this.p = p; this.n = n; }
        public void run() { p.printTable(n); }
    }

    class TestSync {
        public static void main(String args[]) {
            Printer printer = new Printer();
            MyThread t1 = new MyThread(printer, 5);
            MyThread t2 = new MyThread(printer, 100);

            t1.start();
            t2.start();
            // Output will be sequential (entire table of 5, then table of 100)
            // without 'synchronized', lines would mix up.
        }
    }
    ```

***


# **PART 1: UNIT 5 SOLUTIONS**
## **Input-Output, File Operations & Networking**

### **1. I/O and File Handling (C++ & Java)**

#### **Q: Explain Java Serialization in detail. Write a complete program demonstrating saving and retrieving objects.**
**Answer:**
*   **Definition:** Serialization is the process of converting the state of an object into a byte stream (sequence of bytes) to save it to a file or send it over a network. Deserialization is the reverse process.
*   **Key Components:**
    1.  **`Serializable` Interface:** A marker interface (no methods) that a class must implement to be serialized.
    2.  **`ObjectOutputStream`:** Used for writing (serializing) objects.
    3.  **`ObjectInputStream`:** Used for reading (deserializing) objects.
    4.  **`transient` Keyword:** Fields marked `transient` are skipped during serialization.
    5.  **`serialVersionUID`:** A unique ID to verify that the sender and receiver have loaded classes for that object that are compatible.
*   **Code Example:**
    ```java
    import java.io.*;

    // 1. Make class Serializable
    class Student implements Serializable {
        private static final long serialVersionUID = 1L;
        int id;
        String name;
        transient int age; // 'transient' will NOT be saved

        Student(int id, String name, int age) {
            this.id = id; this.name = name; this.age = age;
        }
    }

    public class SerialDemo {
        public static void main(String args[]) {
            Student s1 = new Student(101, "Amit", 20);

            // Serialization (Write)
            try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("student.ser"))) {
                out.writeObject(s1);
                System.out.println("Object Saved.");
            } catch (Exception e) { System.out.println(e); }

            // Deserialization (Read)
            try (ObjectInputStream in = new ObjectInputStream(new FileInputStream("student.ser"))) {
                Student s2 = (Student) in.readObject();
                System.out.println("ID: " + s2.id + " Name: " + s2.name + " Age: " + s2.age);
                // Age will be 0 (default int) because it was transient
            } catch (Exception e) { System.out.println(e); }
        }
    }
    ```

#### **Q: What are streams in C++? Explain the concept of input, output, and error streams.**
**Answer:**
*   **Concept:** A stream is an interface to a flow of data. It acts as a source (input) or destination (output) for data.
*   **Predefined Streams:**
    1.  **`cin` (Standard Input):** Connected to the keyboard (buffered).
    2.  **`cout` (Standard Output):** Connected to the screen (buffered).
    3.  **`cerr` (Standard Error):** Connected to the screen (unbuffered). Used for immediate error output.
    4.  **`clog` (Standard Log):** Connected to the screen (buffered). Used for logging.

#### **Q: Explain console I/O formatting in C++: `setw`, `setprecision`.**
**Answer:**
*   **Formatting Manipulators:**
    *   **`setw(n)`:** Sets the field width to `n` characters. (Right-aligned by default).
    *   **`setprecision(n)`:** Sets the number of digits to display for floating-point numbers.
    *   **`setfill(c)`:** Fills unused field width with character `c`.
*   **Code Example:**
    ```cpp
    #include <iostream>
    #include <iomanip> // Required for manipulators
    using namespace std;

    int main() {
        float PI = 3.14159;
        cout << "Default: " << PI << endl;
        
        // Width 10, fill with '*', precision 3
        cout << setw(10) << setfill('*') << setprecision(3) << PI << endl; 
        // Output: *****3.14 (Total 10 chars)
        return 0;
    }
    ```

#### **Q: Write a C++ program to read a file and count the no. of vowels and consonants.**
**Answer:**
*   **Logic:** Open file using `ifstream`. Read character by character. Check if it's a letter, then check if it's a vowel.
*   **Code Example:**
    ```cpp
    #include <iostream>
    #include <fstream>
    #include <cctype> // for isalpha, tolower
    using namespace std;

    int main() {
        ifstream file("text.txt");
        if (!file) { cout << "File error"; return 1; }

        char ch;
        int v = 0, c = 0;
        
        while (file.get(ch)) { // Read char
            if (isalpha(ch)) {
                ch = tolower(ch);
                if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u')
                    v++;
                else
                    c++;
            }
        }
        cout << "Vowels: " << v << "\nConsonants: " << c << endl;
        file.close();
        return 0;
    }
    ```

#### **Q: Explain two ways to detect EOF (End of File) in C++.**
**Answer:**
*   **Method 1: `eof()` function:** Returns true *after* an attempt to read past the end of the file has been made.
*   **Method 2: `fail()` function:** Returns true if the last I/O operation failed (which includes EOF or format mismatch).
*   **Best Practice:** Check the stream state *immediately* after the read operation.
*   **Code Example:**
    ```cpp
    ifstream file("data.txt");
    char c;
    // WRONG WAY: while(!file.eof()) { file >> c; ... } 
    
    // CORRECT WAY 1: Read inside loop condition
    while(file.get(c)) { 
        cout << c; 
    }
    // Loop terminates automatically on EOF or Error
    ```

#### **Q: Illustrate how class objects can be written and read from the files in C++ (Binary I/O).**
**Answer:**
*   **Concept:** Use `read()` and `write()` functions of `fstream` for binary data. We cast the object address to `char*`.
*   **Code Example:**
    ```cpp
    #include <iostream>
    #include <fstream>
    using namespace std;

    class Student {
    public:
        int roll;
        char name;
        void getData() { cin >> roll >> name; }
        void showData() { cout << roll << " " << name << endl; }
    };

    int main() {
        Student s;
        
        // Write Object
        ofstream outFile("student.dat", ios::binary);
        cout << "Enter Roll & Name: ";
        s.getData();
        outFile.write((char*)&s, sizeof(s)); // Cast to char*
        outFile.close();

        // Read Object
        Student s2;
        ifstream inFile("student.dat", ios::binary);
        inFile.read((char*)&s2, sizeof(s2));
        cout << "Read from file: ";
        s2.showData();
        inFile.close();
        return 0;
    }
    ```

***

### **2. Networking Concepts (Java)**

#### **Q: Explain the client-server model in networking with a simple Java socket example.**
**Answer:**
*   **Concept:**
    *   **Server:** Runs on a specific IP and Port, listening for requests. Uses `ServerSocket`.
    *   **Client:** Initiates connection to the Server's IP and Port. Uses `Socket`.
*   **Steps:**
    1.  Server creates `ServerSocket(port)`.
    2.  Server calls `accept()` (blocks until client connects).
    3.  Client creates `Socket(ip, port)`.
    4.  Both exchange streams (`InputStream`, `OutputStream`).
*   **Code Example:**

    **Server (Server.java):**
    ```java
    import java.io.*;
    import java.net.*;
    public class Server {
        public static void main(String args[]) throws Exception {
            ServerSocket ss = new ServerSocket(6666);
            System.out.println("Waiting for client...");
            Socket s = ss.accept(); // Establish connection
            
            DataInputStream dis = new DataInputStream(s.getInputStream());
            String str = (String) dis.readUTF();
            System.out.println("Client says: " + str);
            
            ss.close();
        }
    }
    ```

    **Client (Client.java):**
    ```java
    import java.io.*;
    import java.net.*;
    public class Client {
        public static void main(String args[]) throws Exception {
            Socket s = new Socket("localhost", 6666);
            
            DataOutputStream dout = new DataOutputStream(s.getOutputStream());
            dout.writeUTF("Hello Server");
            
            dout.flush();
            dout.close();
            s.close();
        }
    }
    ```

***



# **PART 1: UNIT 6 SOLUTIONS**
## **Applets and Java Swing**

### **1. Applets**

#### **Q: What are Applets? Discuss their use. Write a program to print "Hello User".**
**Answer:**
*   **Definition:** An Applet is a small Java program designed to run within a web browser (client-side) or an Applet Viewer. It is an instance of the `java.applet.Applet` class.
*   **Uses:**
    1.  Interactive visualization (graphs, games).
    2.  Immediate feedback to users (calculations).
    3.  Graphics rendering (drawing shapes).
*   **Key Properties:** No `main()` method, restricted security (cannot access local files), runs in a "sandbox".
*   **Code Example:**
    ```java
    import java.applet.Applet;
    import java.awt.Graphics;

    /*
    <applet code="HelloApplet.class" width=300 height=300>
    </applet>
    */

    public class HelloApplet extends Applet {
        public void paint(Graphics g) {
            g.drawString("Hello User", 50, 50);
        }
    }
    ```

#### **Q: Create an applet that contains a button and a text field. Implement event handling for the button click.**
**Answer:**
*   **Concept:** Use `ActionListener` interface to handle clicks. The method `actionPerformed` is triggered when the button is clicked.
*   **Code Example:**
    ```java
    import java.applet.*;
    import java.awt.*;
    import java.awt.event.*;

    public class EventApplet extends Applet implements ActionListener {
        TextField tf;
        Button b;

        public void init() {
            tf = new TextField(20);
            b = new Button("Click Me");
            
            add(tf);
            add(b);
            
            // Register Listener
            b.addActionListener(this);
        }

        public void actionPerformed(ActionEvent e) {
            tf.setText("Button Clicked!");
        }
    }
    ```

#### **Q: Explain Java applets in detail. Create an applet using any 4 functions from `Graphics` class.**
**Answer:**
*   **Lifecycle Methods:**
    1.  `init()`: Called once to initialize variables.
    2.  `start()`: Called after init or when revisiting the page.
    3.  `paint(Graphics g)`: Called to draw output (shapes/text).
    4.  `stop()`: Called when leaving the page.
    5.  `destroy()`: Called before closing to cleanup.
*   **Graphics Functions:**
    *   `drawLine(x1, y1, x2, y2)`
    *   `drawRect(x, y, w, h)`
    *   `drawOval(x, y, w, h)`
    *   `setColor(Color c)`
*   **Code Example:**
    ```java
    import java.applet.*;
    import java.awt.*;

    public class ShapesApplet extends Applet {
        public void paint(Graphics g) {
            g.setColor(Color.RED);
            g.drawLine(10, 10, 100, 10);      // Line
            
            g.setColor(Color.BLUE);
            g.drawRect(10, 30, 100, 50);      // Rectangle
            
            g.setColor(Color.GREEN);
            g.fillRect(10, 100, 100, 50);     // Filled Rectangle
            
            g.setColor(Color.BLACK);
            g.drawOval(150, 30, 50, 50);      // Circle (Oval)
        }
    }
    ```

***

### **2. Java GUI Technologies (Swing/Servlets)**

#### **Q: Write a Java program to design a GUI-based calculator using Swing, including basic event handling.**
**Answer:**
*   **Components:** `JFrame` (Window), `JTextField` (Display), `JButton` (Inputs), `JPanel` (Layout).
*   **Logic:** Store first number and operator when button is clicked. Perform calculation on '=' click.
*   **Code Example:**
    ```java
    import javax.swing.*;
    import java.awt.event.*;

    class Calculator implements ActionListener {
        JFrame f;
        JTextField t;
        JButton b1, b2, b3, bEq, bClr;
        double a=0, b=0, result=0;
        int operator=0;

        Calculator() {
            f = new JFrame("Calc");
            t = new JTextField(); t.setBounds(30, 40, 200, 30);
            
            b1 = new JButton("1"); b1.setBounds(40, 100, 50, 40);
            b2 = new JButton("2"); b2.setBounds(110, 100, 50, 40);
            b3 = new JButton("+"); b3.setBounds(180, 100, 50, 40);
            bEq = new JButton("="); bEq.setBounds(110, 170, 50, 40);
            
            b1.addActionListener(this);
            b2.addActionListener(this);
            b3.addActionListener(this);
            bEq.addActionListener(this);
            
            f.add(t); f.add(b1); f.add(b2); f.add(b3); f.add(bEq);
            f.setSize(300, 300);
            f.setLayout(null);
            f.setVisible(true);
        }

        public void actionPerformed(ActionEvent e) {
            if(e.getSource() == b1) t.setText(t.getText() + "1");
            if(e.getSource() == b2) t.setText(t.getText() + "2");
            if(e.getSource() == b3) {
                a = Double.parseDouble(t.getText());
                operator = 1; // 1 for Add
                t.setText("");
            }
            if(e.getSource() == bEq) {
                b = Double.parseDouble(t.getText());
                if(operator == 1) result = a + b;
                t.setText("" + result);
            }
        }

        public static void main(String args[]) {
            new Calculator();
        }
    }
    ```

#### **Q: Explain the differences between Swing and Servlets in Java.**
**Answer:**
*   **Comparison Table:**

| Feature | Swing | Servlet |
| :--- | :--- | :--- |
| **Type** | GUI Toolkit (Part of JFC) | Server-Side Technology |
| **Execution** | Runs on **Client** machine (Desktop) | Runs on **Web Server** (Server-side) |
| **Interface** | Provides Windows, Buttons, Menus | Processes HTTP Requests/Responses |
| **Use Case** | Creating Desktop Applications (e.g., Calculator) | Creating Web Applications (e.g., Online Banking) |
| **Output** | Graphical User Interface (GUI) | HTML/JSON sent to browser |

*   **Balagurusamy Context:** Swing is for "Look and Feel" on the desktop, while Servlets are the backbone of Java Web Development, extending servers to handle dynamic content.

***


# **PART 2: MID-SEMESTER QUESTIONS**
*(Focused on Concepts, Differences, and Specific Coding Scenarios)*

## **Unit 1: Object Oriented Paradigm & C++ at a Glance**

### **Concepts & Differences**

#### **Q: Method overloading is different from method overriding. Explain.**
**Answer:**
*   **Method Overloading (Compile-Time Polymorphism):**
    *   **Definition:** Defining multiple functions with the **same name** but **different parameters** (type or number) in the *same* class.
    *   **Scope:** Within the same class.
    *   **Resolution:** Decided by compiler (Early Binding).
*   **Method Overriding (Run-Time Polymorphism):**
    *   **Definition:** Redefining a base class function in a derived class with the **same name, same parameters, and same return type**.
    *   **Scope:** Between Base and Derived classes (Inheritance).
    *   **Resolution:** Decided at runtime using `virtual` keyword (Late Binding).

#### **Q: Can destructors be overloaded? Why or why not?**
**Answer:**
*   **No, destructors cannot be overloaded.**
*   **Reason:** A destructor takes no arguments and has no return type. Since overloading requires a difference in the parameter list (signature), and destructors have a fixed signature `~ClassName()`, it is impossible to have more than one destructor in a class.

#### **Q: Why can't we have 'this' pointer with static members?**
**Answer:**
*   **Reason:**
    1.  The `this` pointer holds the address of the *current object instance*.
    2.  **Static members** belong to the *class* as a whole, not to any specific object. They exist even before any object is created.
    3.  Therefore, inside a static member function, there is no "current object" to refer to, so passing a `this` pointer would be meaningless and invalid.

#### **Q: Differentiate between Object-oriented vs Procedure-oriented programming.**
*(Refer to Part 1, Unit 1 for detailed answer. Key points: Top-down vs Bottom-up, Data Hiding, Focus on Algorithms vs Focus on Data).*

#### **Q: Difference: `class variable` vs `static member function`.**
**Answer:**
*   **Class Variable (Static Data Member):**
    *   A variable declared with `static` inside a class.
    *   Shared by all objects. Only one copy exists in memory.
    *   *Usage:* `ClassName::variableName` (if public).
*   **Static Member Function:**
    *   A function declared with `static`.
    *   Can *only* access static data members (Class Variables). Cannot access non-static members.
    *   Called using class name, not object: `ClassName::functionName()`.

#### **Q: Difference between object oriented, object based and pure object oriented languages.**
**Answer:**
*   **Object-Based:** Supports Encapsulation and Object Identity. **No Inheritance/Polymorphism**. (e.g., Early JavaScript, Ada).
*   **Object-Oriented:** Supports Encapsulation + Inheritance + Polymorphism. (e.g., C++, Java, C#).
*   **Pure Object-Oriented:** Everything is an object (including primitives like int, char). No global functions. (e.g., Smalltalk, Ruby). C++ and Java are *hybrid* (not pure) because they use primitive types.

#### **Q: Differentiate Call by value vs call by reference using 'object as argument' concept.**
**Answer:**
*   **Call by Value:**
    *   A copy of the object is created.
    *   Changes made inside the function do **not** affect the original object.
    *   *Cost:* High (invokes Copy Constructor).
*   **Call by Reference:**
    *   The address/reference of the object is passed.
    *   Changes made inside the function **affect** the original object.
    *   *Cost:* Low (no copy created).
    *   *Syntax:* `void func(MyClass &obj) { ... }`

#### **Q: How does `main()` function in C++ differ from `main()` in C? Need of `<iostream>`.**
**Answer:**
*   **Differences:**
    1.  **Return Type:** In standard C++, `main` must return `int`. In C, `void main()` was often permitted (though standard C requires `int` too, older compilers were lenient).
    2.  **Scope:** In C++, `main` cannot be called recursively by the user (standard compliant).
*   **Need of `<iostream>`:** It contains the definitions for the stream objects `cin`, `cout`, `cerr`, etc. Without it, the compiler doesn't know what these standard I/O objects are. It replaces C's `<stdio.h>`.

***

### **Coding & Implementation**

#### **Q: Write code so `S1++` and `++S1` can coexist (Operator Overloading pre/post).**
**Answer:**
*   **Concept:** To distinguish prefix from postfix, C++ adds a dummy `int` argument to the postfix version.
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    class Score {
        int val;
    public:
        Score(int v) : val(v) {}
        void show() { cout << val << endl; }

        // Prefix (++S1)
        void operator++() {
            ++val;
        }

        // Postfix (S1++) - Note the 'int' dummy argument
        void operator++(int) {
            val++;
        }
    };

    int main() {
        Score S1(10);
        ++S1; // Calls operator++() -> 11
        S1.show();
        S1++; // Calls operator++(int) -> 12
        S1.show();
        return 0;
    }
    ```

#### **Q: Write a C++ program using reference variables to swap values.**
**Answer:**
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    void swap(int &a, int &b) { // Receiving addresses (References)
        int temp = a;
        a = b;
        b = temp;
    }

    int main() {
        int x = 100, y = 200;
        cout << "Before: x=" << x << " y=" << y << endl;
        swap(x, y); // Passing variables directly
        cout << "After:  x=" << x << " y=" << y << endl;
        return 0;
    }
    ```

#### **Q: Define a class `Bank Account`. Functions: Init, Deposit, Withdraw, Display.**
**Answer:**
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    class BankAccount {
        char name[30];
        long accNo;
        char type;
        float balance;
    public:
        void init() {
            cout << "Enter Name, AccNo, Type, Balance: ";
            cin >> name >> accNo >> type >> balance;
        }
        void deposit(float amt) {
            balance += amt;
            cout << "Deposited: " << amt << endl;
        }
        void withdraw(float amt) {
            if (balance >= amt) {
                balance -= amt;
                cout << "Withdrawn: " << amt << endl;
            } else {
                cout << "Insufficient Balance!" << endl;
            }
        }
        void display() {
            cout << "Name: " << name << "\nBalance: " << balance << endl;
        }
    };
    ```

#### **Q: Friend function to print sum of digits/reverse (Menu driven).**
**Answer:**
*   **Code Example:**
    ```cpp
    #include <iostream>
    using namespace std;

    class Number {
        int num;
    public:
        void setNum(int n) { num = n; }
        friend void process(Number n);
    };

    void process(Number obj) {
        int choice, n = obj.num;
        cout << "1. Sum of Digits\n2. Reverse\nEnter choice: ";
        cin >> choice;

        if (choice == 1) {
            int sum = 0;
            while(n > 0) { sum += n % 10; n /= 10; }
            cout << "Sum: " << sum << endl;
        } else if (choice == 2) {
            int rev = 0;
            while(n > 0) { rev = rev * 10 + n % 10; n /= 10; }
            cout << "Reverse: " << rev << endl;
        }
    }
    ```

***

## **Unit 2: Dynamic Objects, Operator Overloading & Templates**

### **Dynamic Objects & Pointers**

#### **Q: How is copy constructor used? Explain w.r.t the syntax used.**
**Answer:**
*   **Usage:** It is used to initialize an object using another object of the same class.
*   **Syntax:** `ClassName(const ClassName &obj) { ... }`
*   **When called:**
    1.  `A a2(a1);` (Direct initialization)
    2.  `A a2 = a1;` (Copy initialization)
    3.  Passing object by value to a function.
    4.  Returning object by value from a function.
*   **Example:**
    ```cpp
    Sample S1;
    Sample S2(S1); // Copy Constructor called
    ```

#### **Q: What are `void*` and `size_t`?**
**Answer:**
*   **`void*` (Generic Pointer):** A pointer that has no associated data type. It can hold the address of any type of variable but cannot be dereferenced directly without casting.
    *   *Balagurusamy Context:* Often used in memory allocation functions (`malloc`, generic `new`).
*   **`size_t`:** An unsigned integer type used to represent the size of objects in bytes. It is the return type of the `sizeof` operator.

#### **Q: Differentiate `new operator` and `operator new`.**
**Answer:**
*   **`new operator`:** The keyword used in code (e.g., `new int`). It does two things:
    1.  Allocates memory.
    2.  Calls the constructor.
    *   *Cannot be overloaded.*
*   **`operator new`:** A function that performs the raw memory allocation (similar to `malloc`).
    *   *Can be overloaded* to change how memory is allocated.

#### **Q: What do you mean by dynamic initialization of a variable?**
**Answer:**
*   **Definition:** Initialization of a variable at runtime (during execution) rather than at compile time.
*   **C++ Feature:** In C++, variables can be initialized using expressions or functions anywhere in the code.
*   **Example:**
    ```cpp
    int r;
    cin >> r;
    float area = 3.14 * r * r; // Dynamic Initialization of 'area'
    ```

***

### **Inheritance & Polymorphism**

#### **Q: What is diamond shaped class inheritance problem and how is it solved?**
*(Refer to Part 1, Unit 2 - "Multipath Inheritance". Solution: Virtual Base Class).*

#### **Q: Show the use of initializer list in inheritance using a complete C++ code.**
**Answer:**
*   **Concept:** When a derived class constructor is called, it must initialize the base class parts. An initializer list is used to pass arguments to the Base Class constructor.
*   **Syntax:** `Derived(args) : Base(args) { ... }`
*   **Code Example:**
    ```cpp
    class Base {
        int x;
    public:
        Base(int i) { x = i; cout << "Base Init: " << x << endl; }
    };

    class Derived : public Base {
        int y;
    public:
        // Initializer List calling Base constructor
        Derived(int i, int j) : Base(i) {
            y = j;
            cout << "Derived Init: " << y << endl;
        }
    };
    ```

#### **Q: Differentiate Dynamic binding vs Static Binding.**
*(Refer to Part 1, Unit 2 - "Early binding and Late binding").*

#### **Q: Steps to invoke suitable function if function overloading is done.**
**Answer:**
*   **Balagurusamy/Standard Steps:**
    1.  **Exact Match:** The compiler looks for a function with parameters that exactly match the arguments.
    2.  **Promotion:** If no exact match, it tries to promote arguments (e.g., `char` to `int`, `float` to `double`).
    3.  **Standard Conversion:** If still no match, it tries standard conversions (e.g., `int` to `double`).
    4.  **User-Defined Conversion:** Finally, checks for user-defined conversions (classes).
    *   *Ambiguity:* If multiple matches are found at the same step, the call is ambiguous and flagged as an error.

***

### **Templates**

#### **Q: Where can we use templates in coding? Function templates can be overloaded too - justify.**
**Answer:**
*   **Usage:** Used for Generic Programming (writing code that works for any data type), e.g., Sorting algorithms, Stack/Queue data structures.
*   **Overloading Justification:** Yes, function templates can be overloaded.
    *   You can have a template function `void func(T a)` and a normal function `void func(int a)`.
    *   If you call `func(10)`, the *exact match* (normal function) takes precedence over the template. This allows special behavior for specific types.

#### **Q: Create a derived class template `ColoredBox<T>` that inherits from `Box<T>`.**
**Answer:**
*   **Code Example:**
    ```cpp
    template <class T>
    class Box {
    public:
        T size;
        Box(T s) : size(s) {}
    };

    template <class T>
    class ColoredBox : public Box<T> { // Inherits from Box<T>
        int colorCode;
    public:
        ColoredBox(T s, int c) : Box<T>(s) { // Call Base Constructor
            colorCode = c;
        }
        void show() {
            cout << "Size: " << this->size << " Color: " << colorCode << endl;
        }
    };
    ```

***

**End of Part 2 (Mid-Semester Questions).**