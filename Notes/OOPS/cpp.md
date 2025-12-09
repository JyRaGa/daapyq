
***

# **C++ LEARNING GUIDE (UNITS 1, 2 & C++ Segments of 4, 5)**

## **SECTION 1: The Object-Oriented Paradigm (Theory)**
*(Addresses all questions related to OOP vs POP, Abstraction, Encapsulation, and Language Types)*

**1. What is the fundamental shift from POP to OOP?**
*   **Structured/Procedure-Oriented (POP):** Focuses on **functions** (algorithms). Data is moved openly between functions (often using global data), making it insecure. If data structure changes, all functions break. (e.g., C, Pascal).
*   **Object-Oriented (OOP):** Focuses on **objects**. Data is hidden inside objects (Encapsulation) and can only be accessed by that object's functions. (e.g., C++, Java).
*   **Key Differences:**
    *   **Approach:** POP is Top-Down; OOP is Bottom-Up.
    *   **Security:** POP is less secure (global data); OOP is more secure (private data).
    *   **Unit:** POP's unit is the Function; OOP's unit is the Class.

**2. What is "Abstraction"?**
*   **Definition:** Abstraction is the act of representing essential features without including the background details.
*   **Example:** A switch turns on a light. You care about the interface (the switch), not the internal wiring. In C++, `public` functions provide the interface, hiding the `private` implementation.

**3. What is an "Object"?**
*   **Definition:** An Object is a run-time entity that encapsulates data and the code that operates on that data. It is an instance of a class. It takes up space in memory.

**4. Pure OOP vs Hybrid OOP vs Object-Based.**
*   **Pure OOP (e.g., Smalltalk):** Everything is an object. Even `int` and `char` are objects. No global functions exist.
*   **Hybrid OOP (e.g., C++):** Supports OOP but also allows POP features (global functions, primitive `int`/`float`).
*   **Object-Based (e.g., Early JavaScript/Ada):** Supports **Encapsulation** (Objects) but **NO Inheritance** or **Dynamic Polymorphism**.

***

## **SECTION 2: C++ Basics & Memory Management**
*(Addresses questions on `main`, `namespace`, `new/delete`, `pointers`, `references`)*

**5. What is a Namespace?**
*   **Problem:** If Library A has a function `print()` and Library B has `print()`, they collide.
*   **Solution:** A **namespace** is a named scope that groups identifiers to prevent collisions.
*   **Syntax:** `namespace MySpace { int x; }`. Access via `MySpace::x`.

**6. `new` vs `delete` (Dynamic Memory).**
*   **Static vs Dynamic:**
    *   **Static:** `int a;` (Size fixed at compile time, stored on Stack).
    *   **Dynamic:** `int* p = new int;` (Created at runtime, stored on Heap).
*   **Operators:**
    *   `new`: Allocates memory **AND** calls the constructor. Returns a pointer.
    *   `delete`: Calls the destructor **AND** frees memory.
    *   `delete[]`: MUST be used to delete arrays (`int* p = new int[10]`).
*   **`new` vs `operator new`:**
    *   **`new` operator:** The high-level keyword you use.
    *   **`operator new`:** The low-level function (like `malloc`) that just gets raw bytes.

**7. References (`&`) vs Pointers (`*`).**
*   **Reference:** An alias (another name) for an existing variable. MUST be initialized. Cannot be NULL. `int &ref = x;`
*   **Pointer:** A variable holding a memory address. Can be NULL. Can be reassigned. `int *ptr = &x;`
*   **Call by Reference:** Passing `swap(int &a, int &b)` is cleaner than passing pointers.

***

## **SECTION 3: Classes, Objects, and Members**
*(Addresses questions on Classes, Static, Const, Friend, Nested, Local)*

**8. Class vs Structure vs Union.**
*   **Class:** Members private by default. Reference type in OOP.
*   **Struct:** Members public by default. Used for POD (Plain Old Data).
*   **Union:** All members share the **same** memory location. Size = size of largest member. Only one member active at a time.

**9. Static Data Members (The "Class Variable").**
*   **Concept:** A variable shared by **all** objects of the class. Only one copy exists in memory.
*   **Lifecycle:** Created when program starts, destroyed when program ends.
*   **Syntax:** Declared inside class (`static int count;`), Defined outside (`int Class::count = 0;`).

**10. Const vs Static vs Normal Member Functions.**
*   **Normal:** Can access all data. Called on an object.
*   **Static:** Can **only** access static data. No `this` pointer. Called via Class (`Test::func()`).
*   **Const:** `void func() const;` Promises not to modify *any* member variable of the object.

**11. Friend Functions.**
*   **Concept:** A non-member function given permission to access `private` data.
*   **Why?** Essential for:
    1.  Operator Overloading (e.g., `cout << obj`).
    2.  Functions accessing two different classes (e.g., `add(IT_Student, Mech_Student)`).
*   **Threat to Encapsulation?** Yes, strictly speaking. But useful controlled breach.

**12. Pointer to Members (`.*` and `->*`).**
*   **Concept:** A pointer that stores the "offset" of a member inside a class, not a physical address.
*   **Usage:**
    ```cpp
    int MyClass::*ptr = &MyClass::data; // Pointer to member
    MyClass obj;
    obj.*ptr = 10; // Access
    ```

***

## **SECTION 4: Constructors & Destructors**
*(Addresses questions on Constructor types, Copying, Destructors)*

**13. Constructors (The Initializers).**
*   **Default:** `Class()`. Called if no args provided.
*   **Parameterized:** `Class(int x)`. Initialize with values.
*   **Copy Constructor:** `Class(const Class &obj)`. Creates a new object as a copy of an existing one.
*   **Private Constructor:** Used to **prevent** instantiation (Singleton Pattern).

**14. Shallow Copy vs Deep Copy.**
*   **Shallow:** Copies just the pointer address. Two objects point to the same memory. (Dangerous: Double Free error).
*   **Deep:** Allocates **new** memory and copies the *content*. (Safe).

**15. Destructors.**
*   **Role:** Clean up resources (close files, delete memory) before object dies.
*   **Overloading?** NO. Only one destructor allowed per class (`~Class()`).
*   **Virtual Destructor:** Essential in inheritance. If `Base *b = new Derived; delete b;` is called, a non-virtual base destructor will NOT call the derived destructor, causing leaks.

***

## **SECTION 5: Operator Overloading**
*(Addresses questions on `+`, `+=`, `<<`, `>>`, `++`)*

**16. The Rules.**
*   Cannot change precedence.
*   Cannot create new operators (like `**`).
*   Cannot overload `.`, `::`, `sizeof`, `?:`.

**17. Member vs Friend Overloading.**
*   **Unary (e.g., `-a`):** Member takes 0 args. Friend takes 1 arg.
*   **Binary (e.g., `a + b`):** Member takes 1 arg (Right operand). Friend takes 2 args.
*   **Stream (`cout << a`):** MUST be Friend (because Left operand is `ostream`, not your class).

**18. Type Conversion.**
*   **Basic to Class:** Constructor. `Class(int a) { ... }`
*   **Class to Basic:** Operator Function. `operator int() { return data; }`
*   **Class to Class:** Either Constructor in Destination OR Operator in Source.

***

## **SECTION 6: Inheritance & Polymorphism**
*(Addresses questions on Inheritance types, Virtual functions, Abstract classes)*

**19. Types of Inheritance.**
*   **Single:** A -> B
*   **Multilevel:** A -> B -> C
*   **Multiple:** A, B -> C (C has features of both).
*   **Hierarchical:** A -> B, A -> C.
*   **Hybrid:** Combination (e.g., Diamond).

**20. The Diamond Problem (Virtual Base Class).**
*   **Issue:** A -> B, A -> C, B+C -> D. D has two copies of A. Ambiguity!
*   **Fix:** `class B : virtual public A`. Ensures D gets only one shared copy of A.

**21. Polymorphism (Compile-time vs Run-time).**
*   **Compile-time:** Function Overloading, Operator Overloading. Resolved early. Fast.
*   **Run-time:** Virtual Functions. Resolved late via **vtable** (Virtual Table). Flexible.

**22. Abstract Class & Pure Virtual Functions.**
*   **Pure Virtual:** `virtual void show() = 0;` (No body).
*   **Abstract Class:** A class with at least one pure virtual function. Cannot be instantiated. Used as an interface/blueprint.

***

## **SECTION 7: Templates & STL**
*(Addresses questions on Generic Programming)*

**23. Function Templates vs Class Templates.**
*   **Function:** `template lass T> T add(T a, T b)`. One function logic for all types.
*   **Class:** `template lass T> class Box`. One class definition for `Box<int>`, `Box<float>`, etc.

**24. The STL (Standard Template Library).**
*   **Containers:** `vector` (dynamic array), `list` (linked list), `map` (key-value).
*   **Iterators:** Objects that navigate containers (`v.begin()`, `v.end()`).
*   **Algorithms:** `sort()`, `binary_search()`, `reverse()`.

***

## **SECTION 8: Advanced C++ (Exception Handling & File I/O)**
*(Addresses Unit 4 & 5 C++ questions)*

**25. Exception Handling.**
*   **Keywords:** `try` (code that might fail), `catch` (handle failure), `throw` (report failure).
*   **Rethrowing:** `throw;` inside a catch block passes the error up to the caller.
*   **Catch-All:** `catch(...)` catches any exception type.

**26. File I/O Streams.**
*   **Classes:** `ifstream` (Read), `ofstream` (Write), `fstream` (Both).
*   **Methods:** `open()`, `close()`, `read()`, `write()`, `get()`, `put()`.
*   **EOF detection:** `while(!fin.eof())` or `if(fin.fail())`.

***

## **SECTION 9: The "Big" Coding Problems (The Balagurusamy 8)**
*(The specific coding questions found in your bank)*

1.  **Election/Spoilt Ballot:** Logic: Array `count[6]`. Check `if(vote>=1 && vote<=5)`.
#include <iostream>
using namespace std;

int main() {
    int count[6] = {0}; // Index 1-5 for candidates, count[0] unused
    int spoilt = 0;
    int n, vote;

    cout << "Enter number of voters: ";
    cin >> n;

    for(int i = 0; i < n; i++) {
        cout << "Enter vote (1-5): ";
        cin >> vote;

        if(vote >= 1 && vote <= 5) {
            count[vote]++;
        } else {
            spoilt++;
        }
    }

    cout << "\n--- ELECTION RESULT ---\n";
    for(int i = 1; i <= 5; i++) {
        cout << "Candidate " << i << ": " << count[i] << " votes\n";
    }
    cout << "Spoilt Ballots: " << spoilt << endl;
    return 0;
}

2.  **Matrix Determinant:** 3x3 Math formula implementation.
#include <iostream>
using namespace std;

class Matrix {
    int mat[3][3];
public:
    void getMatrix() {
        cout << "Enter 3x3 Matrix elements:\n";
        for(int i=0; i<3; i++)
            for(int j=0; j<3; j++)
                cin >> mat[i][j];
    }
    
    void determinant() {
        // Formula: a(ei - fh) - b(di - fg) + c(dh - eg)
        int det = mat[0][0] * ((mat[1][1]*mat[2][2]) - (mat[2][1]*mat[1][2])) -
                  mat[0][1] * ((mat[1][0]*mat[2][2]) - (mat[2][0]*mat[1][2])) +
                  mat[0][2] * ((mat[1][0]*mat[2][1]) - (mat[2][0]*mat[1][1]));
                  
        cout << "Determinant: " << det << endl;
    }
};

int main() {
    Matrix m;
    m.getMatrix();
    m.determinant();
    return 0;
}

3.  **Shopping List:** Array manipulation. Removing items requires shifting elements or flagging.
#include <iostream>
using namespace std;

const int MAX = 50;

class Shopping {
    int code[MAX];
    float price[MAX];
    int count;
public:
    Shopping() { count = 0; }
    
    void addItem() {
        cout << "Enter Item Code and Price: ";
        cin >> code[count] >> price[count];
        count++;
    }
    
    void removeItem() {
        int id;
        cout << "Enter Code to remove: ";
        cin >> id;
        for(int i=0; i<count; i++) {
            if(code[i] == id) {
                price[i] = 0; // Logical deletion (simplest for exam)
                code[i] = 0; 
                cout << "Item Removed.\n";
                return;
            }
        }
        cout << "Item not found.\n";
    }
    
    void displayTotal() {
        float sum = 0;
        for(int i=0; i<count; i++) {
            sum += price[i];
        }
        cout << "Total Value: " << sum << endl;
    }
};

int main() {
    Shopping list;
    int opt;
    do {
        cout << "\n1.Add 2.Remove 3.Total 4.Exit\nOption: ";
        cin >> opt;
        switch(opt) {
            case 1: list.addItem(); break;
            case 2: list.removeItem(); break;
            case 3: list.displayTotal(); break;
        }
    } while(opt != 4);
    return 0;
}


4.  **Complex Number Addition:** Friend function `operator+(Complex a, Complex b)`.
5.  **String Class:** Deep copy in constructor. Overload `+` (Concat) and `+=`.
6.  **Vector Min Value:** Template function `T min(T arr[])`.
7.  **Object Counter:** Static member `count` incremented in Constructor, decremented in Destructor.
8.  **File Vowel Counter:** Read chars loop. Check `if(vowel)`.

***

## **SECTION 10: Extra Unit 1 Concepts (Advanced Theory)**

**1. Constant pointer vs pointer to constant.**

- `const int* p;` – **Pointer to constant int.**  
  You **cannot change the value** through `p` (`*p = 5;` is illegal), but you **can change** `p` to point somewhere else (`p = &x;` is fine).
- `int* const p;` – **Constant pointer to int.**  
  You **can change the value** through `p` (`*p = 5;` is fine), but you **cannot reassign** `p` to a different address.
- `const int* const p;` – **Constant pointer to constant int.**  
  Neither the pointer nor the pointee can change.

```cpp
int x = 10, y = 20;
const int* p1 = &x;   // *p1 read-only, p1 can move
int* const p2 = &x;   // *p2 modifiable, p2 fixed
const int* const p3 = &x; // both fixed
```

***

**2. Stack mechanism for function calls (activation records).**

When a function is called, the system uses a **stack frame (activation record)** to store:  

- **Return address** (where to continue after function ends).  
- **Parameters** (passed by value / address).  
- **Local variables** of the function.  

Process:

1. Caller pushes arguments and return address, control jumps to callee.  
2. Callee allocates space for locals on the stack (usually by adjusting stack pointer).  
3. On `return`, locals go out of scope, stack pointer is restored, return address is popped, and execution resumes at caller.  

In C++, each nested call creates a new frame; recursion is just repeated frame creation until base case.

***

**3. Variable scope & lifetime; global vs local vs block; static vs automatic vs dynamic.**

- **Scope** (where it is visible):
  - *Global:* Declared outside all functions; visible from that point to end of file (or across files via `extern`).
  - *Local:* Declared inside a function; only visible within that function.
  - *Block:* Declared inside `{}`; visible only within that block.

- **Lifetime** (how long it exists):
  - *Automatic (`auto`, default):* Created when control enters the block, destroyed when it leaves.
  - *Static (`static`):* Created once at program start, destroyed at program end, but may have local scope.
  - *Dynamic (`new` / `delete`):* Lifetime controlled manually by allocation and deallocation.

```cpp
int g = 0;        // global, static lifetime

void f() {
    static int s = 0; // local scope, static lifetime
    int a = 0;        // local scope, automatic lifetime
    int* p = new int; // dynamic
    delete p;
}
```

***

**4. Tokens, keywords, identifiers, constants.**

- **Token:** Smallest unit in a C++ program: keywords, identifiers, constants, operators, punctuation.  
- **Keyword:** Reserved word with special meaning, e.g. `int`, `class`, `public`, `virtual`.  
- **Identifier:** Name given to variables, functions, classes, etc. Must start with letter or `_`, then letters/digits/`_`, cannot be keyword.  
- **Constant:** Fixed value that does not change during execution: numeric (`10`, `3.14`), character (`'A'`), string (`"Hello"`), symbolic (`const int N = 100;`).

***

**5. Inline functions & when inline expansion may not work.**

- A function **defined inside the class** body is *treated as `inline` by default* (the compiler is allowed to inline it but is not forced to).  
- Situations where the compiler usually **refuses to inline**:
  - The function is **recursive**.
  - It has **loops** or large/complex control flow (`switch`, heavy `if-else`).
  - It takes the **address** of the function (function pointer).
  - It is too **large**; compiler decides inlining would hurt performance.

The `inline` keyword is a *hint* to the compiler, not a guarantee.

***

## **SECTION 11: Extra Unit 1 Programs & Design Questions**

**6. Mutual friend classes (bidirectional friendship).**

Two classes can each declare the other as a `friend`, allowing full mutual access to private members.

```cpp
#include <iostream>
using namespace std;

class B; // forward declaration

class A {
    int x;
public:
    A(int v) : x(v) {}
    friend class B; // B can access A's private members
};

class B {
    int y;
public:
    B(int v) : y(v) {}
    friend class A; // A can access B's private members
    void showSum(A a) {
        cout << "Sum: " << (a.x + y) << endl;
    }
};

int main() {
    A objA(10);
    B objB(20);
    objB.showSum(objA);
}
```

***

**7. Accessing members: from `main`, from same class, from another class.**

Given:

```cpp
class Sample {
    int a;
public:
    int b;
    void set(int x, int y) { a = x; b = y; }  // member of same class
    void show() { cout << a << " " << b; }
};
```

- **Inside `main`:**

```cpp
Sample s;
s.b = 10;        // OK (public)
s.set(5, 10);    // OK (public)
 // s.a = 5;     // ERROR: 'a' is private
```

- **Inside member function of same class:**  
  `set` and `show` can access both `a` and `b` directly; private/public distinction doesn’t matter inside the same class.

- **Inside member function of another class:**  
  Cannot access `a` or `b` directly unless:
  - it is declared `friend` inside `Sample`, or  
  - it accesses through public members of `Sample`.

***

**8. Object counter using static members (created/destroyed/active).**

```cpp
#include <iostream>
using namespace std;

class Counter {
    static int created;
    static int destroyed;
public:
    Counter()  { created++; }
    ~Counter() { destroyed++; }

    static void report() {
        cout << "Created: "   << created   << endl;
        cout << "Destroyed: " << destroyed << endl;
        cout << "Active: "    << created - destroyed << endl;
    }
};

int Counter::created   = 0;
int Counter::destroyed = 0;

int main() {
    Counter c1, c2;
    {
        Counter c3;
        Counter::report();
    } // c3 destroyed here
    Counter::report();
}
```

***

**9. TravelPlan and MetroTrain classes.**

```cpp
#include <iostream>
#include <string>
using namespace std;

class TravelPlan {
    int PlanCode;
    string Place;
    int NumberOfTravellers;
    int NumberOfBuses;
public:
    TravelPlan(int pc=1001, string pl="Agra", int nt=5)
        : PlanCode(pc), Place(pl), NumberOfTravellers(nt) {
        if (nt < 20)      NumberOfBuses = 1;
        else if (nt < 40) NumberOfBuses = 2;
        else              NumberOfBuses = 3;
    }
    void NewPlan() {
        cout << "Enter PlanCode, Place, Travellers: ";
        cin >> PlanCode >> Place >> NumberOfTravellers;
        if (NumberOfTravellers < 20)      NumberOfBuses = 1;
        else if (NumberOfTravellers < 40) NumberOfBuses = 2;
        else                              NumberOfBuses = 3;
    }
    void ShowPlan() const {
        cout << PlanCode << " " << Place << " "
             << NumberOfTravellers << " " << NumberOfBuses << endl;
    }
};

class MetroTrain {
    int TrainNo;
    string TrainName, Source, Destination;
    string JourneyDateTime;
    int Capacity;
public:
    MetroTrain(int tn=0, string name="", string src="",
               string dest="", string dt="", int cap=0)
        : TrainNo(tn), TrainName(name), Source(src),
          Destination(dest), JourneyDateTime(dt), Capacity(cap) {}
    void input() {
        cout << "Enter TrainNo, Name, Source, Destination, DateTime, Capacity:\n";
        cin >> TrainNo >> TrainName >> Source >> Destination >> JourneyDateTime >> Capacity;
    }
    void display() const {
        cout << TrainNo << " " << TrainName << " " << Source << " "
             << Destination << " " << JourneyDateTime << " " << Capacity << endl;
    }
};
```

***

**10. Explicit destructor calls and when they are useful.**

Normally, destructors are called automatically when an object goes out of scope or when `delete` is used. You *can* call a destructor explicitly:

```cpp
obj.~ClassName();   // explicit call
```

Use cases (advanced):

- Manually destroying an object constructed via **placement new**, while reusing the same memory for another object of the same type.
- Testing / debugging lifetime logic.

You must **not** call the destructor explicitly on objects that will also go out of scope and be destroyed automatically; doing so causes **double destruction** and undefined behavior.

***

## **SECTION 12: Extra Unit 2 – Operator Overloading & Conversions**

**11. Class-to-class type conversion: Polar → Rectangular.**

**Method 1 – Conversion constructor (in destination class):**

```cpp
class Polar {
public:
    double r, theta; // radius, angle in radians
    Polar(double rr=0, double tt=0) : r(rr), theta(tt) {}
};

class Rect {
    double x, y;
public:
    Rect(double xx=0, double yy=0) : x(xx), y(yy) {}
    // Conversion constructor
    Rect(const Polar& p) {
        x = p.r * cos(p.theta);
        y = p.r * sin(p.theta);
    }
};
```

**Method 2 – Conversion operator (in source class):**

```cpp
class Rect; // forward decl

class Polar {
public:
    double r, theta;
    Polar(double rr=0, double tt=0) : r(rr), theta(tt) {}
    operator Rect(); // declaration
};

class Rect {
    double x, y;
public:
    Rect(double xx=0, double yy=0) : x(xx), y(yy) {}
    friend class Polar;
};

Polar::operator Rect() {
    return Rect(r * cos(theta), r * sin(theta));
}
```

- Use a **conversion constructor** when you control / can modify the destination class.  
- Use a **conversion operator** when you want the source class to be convertible to many targets or you cannot modify the destination.

***

**12. Rational class with +, -, *, /.**

```cpp
class Rational {
    int num, den;
    void reduce(); // optional: normalize fraction
public:
    Rational(int n=0, int d=1) : num(n), den(d) {}

    Rational operator+(const Rational& r) const {
        return Rational(num*r.den + r.num*den, den*r.den);
    }
    Rational operator-(const Rational& r) const {
        return Rational(num*r.den - r.num*den, den*r.den);
    }
    Rational operator*(const Rational& r) const {
        return Rational(num*r.num, den*r.den);
    }
    Rational operator/(const Rational& r) const {
        return Rational(num*r.den, den*r.num);
    }
};
```

Example: `Rational(1,2) + Rational(1,3)` gives `Rational(5,6)`.

***

**13. Overloading global `new` and `delete` to track memory.**

```cpp
#include <new>
#include <iostream>
using namespace std;

size_t totalAllocated = 0;

void* operator new(size_t sz) {
    totalAllocated += sz;
    cout << "Allocating " << sz << " bytes. Total: " << totalAllocated << endl;
    if (void* p = std::malloc(sz)) return p;
    throw bad_alloc();
}

void operator delete(void* p, size_t sz) noexcept {
    totalAllocated -= sz;
    cout << "Freeing " << sz << " bytes. Total: " << totalAllocated << endl;
    std::free(p);
}
```

This tracks total allocated and deallocated bytes across the entire program.

***

## **SECTION 13: Extra Unit 2 – Templates & Examples**

**14. Template recursion – factorial.**

```cpp
template <typename T>
T fact(T n) {
    if (n <= 1) return 1;
    return n * fact(n - 1); // recursive template function
}
```

**15. Template inheritance – Box<T> → ColoredBox<T>.**

```cpp
template lass T>
class Box {
protected:
    T value;
public:
    Box(T v) : value(v) {}
    T get() const { return value; }
};

template lass T>
class ColoredBox : public Box<T> {
    string color;
public:
    ColoredBox(T v, string c) : Box<T>(v), color(c) {}
    void show() const {
        cout << this->value << " in color " << color << endl;
    }
};
```

**16. Pair<T> with `get_min()` among three values.**

```cpp
template lass T>
class Triple {
    T a, b, c;
public:
    Triple(T x, T y, T z) : a(x), b(y), c(z) {}
    T get_min() const {
        T m = a;
        if (b < m) m = b;
        if (c < m) m = c;
        return m;
    }
};
```

**17. Template function `max(T, int)`.**

```cpp
template <typename T>
T mymax(T a, int b) {
    return (a > static_cast<T>(b)) ? a : static_cast<T>(b);
}
```

**18. Swap template usable with `int`, `float`, `string`.**

```cpp
template lass T>
void myswap(T& a, T& b) {
    T temp = a;
    a = b;
    b = temp;
}
```

***
Here are **mid-sem–specific C++ blocks** you can append after the existing sections in `cpp.txt`. They are grouped by Unit and match your mid-term PYQs.

***

## **SECTION 14: Mid-Sem Unit 1 – Key Concepts**

**1. Method overloading vs method overriding.**

- **Overloading (compile-time / static polymorphism):**
  - Same function name, **different parameter list** (type, number, or order).
  - Occurs **within the same class** (or between base/derived if signatures differ).
  - Resolved at compile time based on argument types.

```cpp
class A {
public:
    void show(int x);
    void show(double x); // overloaded
};
```

- **Overriding (run-time / dynamic polymorphism):**
  - Same function signature in **base and derived** classes.
  - Base function must be `virtual`, and call is resolved at **run time** via base pointer/reference.

```cpp
class Base {
public:
    virtual void show();
};
class Derived : public Base {
public:
    void show() override; // overrides Base::show
};
```

***

**2. Can destructors be overloaded? Why or why not?**

No. A class can have **only one destructor**, with:

- Fixed name: `~ClassName()`.
- **No parameters** and **no return type**.

Because of this, there is **no way** to distinguish multiple destructor overloads by argument list, so C++ does not allow destructor overloading.

***

**3. Why is there no `this` pointer with static members?**

- `this` points to **the current object** (`ClassName* const`).
- A **static member function**:
  - Belongs to the **class, not any instance**.
  - Can be called as `ClassName::func()` with **no object**.
- Therefore, there is no current object; no `this` pointer exists inside static member functions. Any attempt to use `this` in a static function is a compile-time error.

***

**4. Class variable vs static member function.**

- **Class variable (static data member):**
  - One copy shared by all objects.
  - Syntax: `static int count;` inside class, `int Class::count = 0;` outside.
  - Can be accessed by `Class::count` or via object `obj.count` (though the former is clearer).

- **Static member function:**
  - Belongs to class, not object.
  - Syntax: `static void showCount();`
  - No `this` pointer; can only access **static** data/functions.
  - Called as `Class::showCount();`

***

**5. Call by value vs call by reference using object as argument.**

```cpp
class Test {
public:
    int x;
};

// Call by value
void func1(Test t) { t.x = 100; } // modifies copy

// Call by reference
void func2(Test& t) { t.x = 200; } // modifies original
```

In `func1`, the original object is unchanged; in `func2`, `x` of the original object is modified. With large objects, call by reference is both **faster** and **allows modification**.

***

**6. C vs C++ `main()`; need of `<iostream>`.**

- In **C**:
  ```c
  int main() {
      printf("Hello");
      return 0;
  }
  ```
- In **C++**:
  ```cpp
  #include <iostream>
  using namespace std;

  int main() {
      cout << "Hello";
      return 0;
  }
  ```

Differences:

- C uses `<stdio.h>` and functions like `printf`, `scanf`.
- C++ encourages `<iostream>` with `cin`, `cout`, which are **objects** of classes (`istream`, `ostream`) and support operator overloading (`<<`, `>>`), type safety, and extensibility.

***

**7. Are member functions defined inside the class inline by default?**

Conceptually **yes**, but with nuance:

- Any function **defined inside** a class definition is treated as if it were declared `inline`.
- The compiler is **free to ignore** this suggestion.
- Very large or complex inside-class definitions may not actually be inlined; the compiler decides based on optimization criteria.

***

## **SECTION 15: Mid-Sem Unit 1 – Programs**

**8. Overload both `++S1` (prefix) and `S1++` (postfix).**

```cpp
#include <iostream>
using namespace std;

class Score {
    int val;
public:
    Score(int v=0) : val(v) {}

    // Prefix ++S1
    Score& operator++() {
        ++val;
        return *this;
    }

    // Postfix S1++
    Score operator++(int) {
        Score temp = *this; // save old value
        val++;
        return temp;        // return old value
    }

    void show() const { cout << val << endl; }
};

int main() {
    Score s(5);
    (++s).show(); // 6
    (s++).show(); // prints 6, then s becomes 7
    s.show();     // 7
}
```

***

**9. Swap two values using reference variables.**

```cpp
#include <iostream>
using namespace std;

void swapRef(int& a, int& b) {
    int temp = a;
    a = b;
    b = temp;
}

int main() {
    int x = 10, y = 20;
    swapRef(x, y);
    cout << x << " " << y; // 20 10
}
```

***

**10. Bank Account class (Init, Deposit, Withdraw, Display).**

```cpp
#include <iostream>
#include <string>
using namespace std;

class BankAccount {
    string name;
    long accNo;
    string type;
    double balance;
public:
    void init(string n, long a, string t, double b) {
        name = n; accNo = a; type = t; balance = b;
    }
    void deposit(double amt) {
        balance += amt;
    }
    void withdraw(double amt) {
        if (amt > balance)
            cout << "Insufficient balance\n";
        else
            balance -= amt;
    }
    void display() const {
        cout << "Name: " << name << " Balance: " << balance << endl;
    }
};
```

***

**11. Distance class with parameterized constructor and defaults.**

```cpp
class Distance {
    int feet;
    float inches;
public:
    Distance(int f=0, float i=0.0f) : feet(f), inches(i) {}

    void show() const {
        cout << feet << " ft " << inches << " in\n";
    }
};
```

***

**12. Time class – add two time objects.**

```cpp
class Time {
    int hr, min, sec;
public:
    Time(int h=0, int m=0, int s=0) : hr(h), min(m), sec(s) {}

    Time add(const Time& t) const {
        Time res;
        res.sec = sec + t.sec;
        res.min = min + t.min + res.sec / 60;
        res.sec %= 60;
        res.hr  = hr + t.hr + res.min / 60;
        res.min %= 60;
        return res;
    }

    void show() const {
        cout << hr << ":" << min << ":" << sec << endl;
    }
};
```

***

## **SECTION 16: Mid-Sem Unit 2 – Concepts**

**13. Copy constructor usage & syntax.**

- Declaration: `ClassName(const ClassName& other);`
- Called when:
  - Object is initialized from another: `ClassName b = a;`
  - Passed by value to a function.
  - Returned by value from a function (before NRVO).

```cpp
class Sample {
    int x;
public:
    Sample(int v=0) : x(v) {}
    Sample(const Sample& s) : x(s.x) {} // copy ctor
};
```

***

**14. `void*` and `size_t`.**

- `void*` – **generic pointer**:
  - Can hold address of any data type.
  - Cannot be dereferenced directly; must be **cast** back to correct type.

```cpp
void* p;
int x = 10;
p = &x;
// int y = *p; // ERROR
int y = *(static_cast<int*>(p)); // OK
```

- `size_t` – unsigned integer type used for sizes, returned by `sizeof`, portable across platforms:

```cpp
size_t n = sizeof(int); // typically 4
```

***

**15. Dynamic initialization of a variable.**

Initialization using a **non-constant expression** evaluated at run time, often at the place of declaration:

```cpp
int n;
cin >> n;
int* arr = new int[n]; // n is not known at compile time
```

C++ allows such dynamic initialization; C traditionally required constant expressions for some contexts.

***

**16. Dynamic vs static binding.**

- **Static binding (early binding):**
  - Function call resolved at compile time.
  - Non-virtual functions, overloaded functions.

- **Dynamic binding (late binding):**
  - Achieved via **virtual functions**.
  - Call resolved at run time based on actual object type.

```cpp
Base* p = new Derived;
p->show(); // if show is virtual, dynamic binding chooses Derived::show
```

***

**17. Purpose of pure virtual function vs normal virtual.**

- `virtual void f();` – normal virtual:
  - Has an implementation in base.
  - Derived can override, but not forced.

- `virtual void f() = 0;` – **pure virtual**:
  - No implementation in base.
  - Makes the class **abstract**.
  - All non-abstract derived classes **must** override it.

***

**18. Steps used by compiler to choose an overloaded function.**

Given multiple overloads, the compiler:

1. Builds a **candidate set** of functions with matching name and accessible scope.
2. Filters it to a **viable set** whose parameters can accept the given arguments (possibly with conversions).
3. Ranks conversions to find the **best match**:
   - Exact match > promotion > standard conversion > user-defined conversion.
4. If a unique best match exists → used. If two are equally good → **ambiguity error**.

***

**19. Role of `::` in inheritance.**

- Used to **qualify** which class’s member you want when there is ambiguity.

```cpp
class Base {
public:
    void show();
};
class Derived : public Base {
public:
    void show();
    void callBase() { Base::show(); } // explicitly call Base version
};
```

***

**20. Diamond inheritance problem and virtual base solution (mid-sem view).**

```cpp
class A { public: int x; };
class B : virtual public A {};
class C : virtual public A {};
class D : public B, public C {};

int main() {
    D obj;
    obj.x = 10; // single A subobject, no ambiguity
}
```

Without `virtual`, `D` would contain **two separate A bases**, and `obj.x` would be ambiguous.

***

## **SECTION 17: Mid-Sem Unit 2 – Programs & Templates**

**21. Program showing virtual base class (explicit).**

```cpp
#include <iostream>
using namespace std;

class Student {
protected:
    int roll;
public:
    void get_roll(int r) { roll = r; }
};

class Test : virtual public Student {
protected:
    int marks;
public:
    void get_marks(int m) { marks = m; }
};

class Sports : virtual public Student {
protected:
    int score;
public:
    void get_score(int s) { score = s; }
};

class Result : public Test, public Sports {
public:
    void display() {
        cout << "Roll: " << roll
             << " Marks: " << marks
             << " Score: " << score
             << " Total: " << marks + score << endl;
    }
};
```

***

**22. STRING class: `s3 = s1 + s2;` using copy constructor.**

```cpp
#include <iostream>
#include string>
using namespace std;

class String {
    char* str;
public:
    String(const char* s = "") {
        str = new char[strlen(s)+1];
        strcpy(str, s);
    }
    // Copy constructor
    String(const String& other) {
        str = new char[strlen(other.str)+1];
        strcpy(str, other.str);
    }
    // Concatenation
    String operator+(const String& s) const {
        size_t len = strlen(str) + strlen(s.str);
        char* buf = new char[len+1];
        strcpy(buf, str);
        strcat(buf, s.str);
        String temp(buf); // uses constructor
        delete[] buf;
        return temp;      // copy elision / copy ctor
    }
    void show() const { cout << str << endl; }
    ~String() { delete[] str; }
};
```

***

**23. Show use of initializer list in inheritance.**

```cpp
class Base {
    int x;
public:
    Base(int a) : x(a) {}
};

class Derived : public Base {
    int y;
public:
    Derived(int a, int b) : Base(a), y(b) {} // initializer list
};
```

The order of initialization is **base first**, then members, regardless of the order in initializer list.

***

**24. Where are templates useful? Overloaded function templates.**

- Use templates when you want the **same logic** to work for multiple types: `int`, `double`, `string`, etc.
- Function templates themselves can be overloaded:

```cpp
template lass T>
T maxVal(T a, T b) { return (a > b) ? a : b; }

// Overload with (T, int)
template lass T>
T maxVal(T a, int b) { return (a > (T)b) ? a : (T)b; }
```

Both are templates (different parameter lists), so this is **template overloading**.

***

**25. Derived template `ColoredBox<T>` from `Box<T>`.**

Already given earlier (see Section 13); this exactly matches the mid-sem template inheritance question.

***

**26. Function template `max(T, int)` mid-sem version.**

```cpp
template <typename T>
T maxVal(T a, int b) {
    return (a > static_cast<T>(b)) ? a : static_cast<T>(b);
}
```

***

## **SECTION 15: Additional Critical Concepts (Unit 1 Gaps)**
*(Essential definitions missing from previous sections)*

**1. Array of Pointers vs. Pointer to Array.**
*   **Array of Pointers (`int* arr[3]`):** 
    *   **Concept:** An array where *each element* is a pointer. It holds 3 separate addresses.
    *   **Use Case:** Storing a list of strings (`char* names[]`) or a ragged array (rows of different lengths).
    *   **Memory:** Creates 3 separate pointer variables.
*   **Pointer to Array (`int (*ptr)[3]`):** 
    *   **Concept:** A single pointer variable that points to an *entire array* of size 3.
    *   **Use Case:** Passing a 2D array to a function while preserving its dimensions.
    *   **Memory:** Creates only 1 pointer variable.

**2. Local Class.**
*   **Definition:** A class defined **inside a function** body.
*   **Scope:** It is only visible/usable within that specific function.
*   **Restrictions:** 
    *   It cannot have static data members.
    *   It can only access `static` variables of the enclosing function (it cannot access the function's local variables unless they are passed to it).
    *   It is rarely used in practice but appears in exam theory questions.

**3. RVO (Return Value Optimization).**
*   **Problem:** When a function returns an object by value (e.g., `return Matrix(10);`), the compiler standardly creates a temporary copy, copies it to the caller, and then destroys the temp. This is slow.
*   **Solution (RVO):** A compiler optimization technique where the temporary copy is eliminated. The compiler constructs the object *directly* in the memory location of the variable that is supposed to receive it.
*   **Result:** Faster execution for functions returning large objects.

***
