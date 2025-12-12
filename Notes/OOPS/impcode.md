Use github Outline (sidebar) to navigate
***

### **UNIT 1: Classes & Basics**

#### **1. Basic Class with Constructors (Parameterized & Copy)**
*Concepts: Encapsulation, Constructor Overloading*
```cpp
class Student {
    int id;
public:
    // Default Constructor
    Student() { id = 0; }
    // Parameterized Constructor
    Student(int x) { id = x; }
    // Copy Constructor (Explicit)
    Student(const Student &s) { id = s.id; }
    
    void display() { cout << id << endl; }
};
```

#### **2. Static Members (Shared Counter)**
*Concepts: `static` keyword, Scope Resolution `::`*
```cpp
class Item {
    static int count; // Declaration
public:
    Item() { count++; }
    static void showCount() { cout << count; }
};
// Definition (MUST be outside)
int Item::count = 0;

int main() {
    Item a, b; 
    Item::showCount(); // Output: 2
}
```

#### **3. Friend Function (Adding 2 Complex Numbers)**
*Concepts: Accessing private data externally*
```cpp
class Complex {
    int r, i;
public:
    Complex(int real=0, int imag=0) : r(real), i(imag) {}
    friend Complex add(Complex c1, Complex c2);
    void show() { cout << r << "+" << i << "i"; }
};

Complex add(Complex c1, Complex c2) {
    return Complex(c1.r + c2.r, c1.i + c2.i);
}
```

#### **4. Inline Function**
*Concepts: Optimization*
```cpp
inline int square(int x) {
    return x * x;
}
// Compiler replaces 'square(5)' with '5*5' directly.
```

***

### **UNIT 2: Dynamic Memory & Overloading**

#### **5. Dynamic Allocation (New/Delete)**
*Concepts: Heap memory, Pointers*
```cpp
void dynamicDemo() {
    int* ptr = new int;      // Single Int
    *ptr = 10;
    delete ptr;              // Free Single

    int* arr = new int[5];   // Array
    delete[] arr;            // Free Array
}
```

#### **6. Operator Overloading (Unary `-`)**
*Concepts: Changing sign of coordinates*
```cpp
class Point {
    int x, y;
public:
    Point(int a, int b) : x(a), y(b) {}
    // Overload unary minus
    void operator-() {
        x = -x;
        y = -y;
    }
};
// Usage: Point p(10, 20); -p; // x becomes -10
```

#### **7. Operator Overloading (Binary `+`)**
*Concepts: Adding two objects*
```cpp
class String {
    // Simplified logic (usually uses char*)
    int val; 
public:
    String(int v) : val(v) {}
    String operator+(String s) {
        return String(val + s.val);
    }
};
```

#### **8. Type Conversion (Basic to Class)**
*Concepts: Conversion Constructor*
```cpp
class Time {
    int hrs;
public:
    // Converts int (mins) to Time object
    Time(int mins) {
        hrs = mins / 60;
    }
};
// Usage: Time t = 120; // Automatically calls constructor
```

***

### **UNIT 3: Inheritance**

#### **9. Single & Multilevel Inheritance**
*Concepts: Base -> Derived*
```cpp
class Student { protected: int roll; };
class Test : public Student { protected: int marks; };
class Result : public Test {
public:
    void show() { cout << roll << " " << marks; }
};
```

#### **10. Virtual Function (Runtime Polymorphism)**
*Concepts: Late Binding, Overriding*
```cpp
class Base {
public:
    virtual void show() { cout << "Base"; }
};
class Derived : public Base {
public:
    void show() { cout << "Derived"; }
};

int main() {
    Base* ptr;
    Derived d;
    ptr = &d;
    ptr->show(); // Output: "Derived" (Magic of Virtual)
}
```

#### **11. Virtual Destructor**
*Concepts: Preventing Memory Leaks*
```cpp
class Base {
public:
    virtual ~Base() { cout << "Base Destructed"; }
};
class Derived : public Base {
    int* p;
public:
    Derived() { p = new int; }
    ~Derived() { delete p; cout << "Derived Destructed"; }
};
// Usage: Base* b = new Derived(); delete b; 
// Without virtual ~Base(), Derived destructor would NEVER run!
```

#### **12. Diamond Problem (Virtual Base Class)**
*Concepts: Ambiguity Resolution*
```cpp
class A { public: int x; };
class B : virtual public A {}; // Note 'virtual'
class C : virtual public A {}; // Note 'virtual'
class D : public B, public C {};

// Usage: D obj; obj.x = 10; // Works! (Only one copy of x)
```

***

### **UNIT 4: Templates & Exceptions**

#### **13. Function Template (Swap)**
*Concepts: Generic Programming*
```cpp
template <class T>
void swapVals(T &a, T &b) {
    T temp = a;
    a = b;
    b = temp;
}
// Usage: swapVals(x, y); works for int, float, char...
```

#### **14. Class Template (Calculator)**
*Concepts: Generic Classes*
```cpp
template <class T>
class Calc {
    T num1, num2;
public:
    Calc(T n1, T n2) : num1(n1), num2(n2) {}
    T add() { return num1 + num2; }
};
// Usage: Calc<int> c(10, 20);
```

#### **15. Exception Handling (Try-Catch)**
*Concepts: Error Safety*
```cpp
void divide(int a, int b) {
    try {
        if (b == 0) throw "Division by Zero";
        cout << a / b;
    }
    catch (const char* msg) {
        cout << "Error: " << msg;
    }
}
```

***

### **UNIT 5: File Handling**

#### **16. File I/O (Read/Write)**
*Concepts: fstream*
```cpp
#include <fstream>
void fileDemo() {
    // Writing
    ofstream out("test.txt");
    out << "Hello World";
    out.close();

    // Reading
    ifstream in("test.txt");
    string line;
    in >> line;
    cout << line;
    in.close();
}
```

***

### **Missing / "Enhance" Topics**

#### **17. Local Class**
```cpp
void fun() {
    class Local { // Defined inside function
    public:
        void msg() { cout << "Hidden Class"; }
    };
    Local l; l.msg();
}
```

#### **18. Overloading `new` and `delete`**
```cpp
void* operator new(size_t size) {
    return malloc(size); // Custom allocation
}
void operator delete(void* p) {
    free(p); // Custom deallocation
}
```

This list is exhaustive for your exam. If a code question comes, it will be one of these 18 logic patterns.
