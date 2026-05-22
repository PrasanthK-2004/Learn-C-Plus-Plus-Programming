# C++ Virtual Functions

## What is a Virtual Function?

A **virtual function** is a member function in a base class that is **redefined in a derived class**, and allows **runtime polymorphism (dynamic dispatch)**.

👉 It is used when function call must be decided at **runtime**, not compile time.

# 1. Basic Virtual Function Example

## Program

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    virtual void show()
    {
        cout << "Base Class Function" << endl;
    }
};

class Derived : public Base
{
public:
    void show()
    {
        cout << "Derived Class Function" << endl;
    }
};

int main()
{
    Base *ptr;
    Derived obj;

    ptr = &obj;

    ptr->show();

    return 0;
}
```

---

## Output

```text
Derived Class Function
```

---

# Why Virtual Function is Needed?

Without `virtual`, function call is resolved using **static binding**.

### Without virtual:

```cpp
Base *ptr = &obj;
ptr->show();  // Base function called
```

### With virtual:

👉 Runtime decides actual object type  

👉 Calls Derived function

---

# 2. Virtual Function with Multiple Objects

## Program

```cpp
#include <iostream>
using namespace std;

class Animal
{
public:
    virtual void sound()
    {
        cout << "Animal Sound" << endl;
    }
};

class Dog : public Animal
{
public:
    void sound()
    {
        cout << "Dog Barks" << endl;
    }
};

class Cat : public Animal
{
public:
    void sound()
    {
        cout << "Cat Meows" << endl;
    }
};

int main()
{
    Animal *ptr;

    Dog d;
    Cat c;

    ptr = &d;
    ptr->sound();

    ptr = &c;
    ptr->sound();

    return 0;
}
```

---

## Output

```text
Dog Barks
Cat Meows
```

---

# 3. Pure Virtual Function (Abstract Class)

## Concept

A function with no implementation in base class.

```cpp
virtual void show() = 0;
```

## Program

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    virtual void show() = 0; // Pure virtual
};

class Derived : public Base
{
public:
    void show()
    {
        cout << "Derived Implementation" << endl;
    }
};

int main()
{
    Derived obj;
    obj.show();

    return 0;
}
```

---

## Output

```text
Derived Implementation
```

---

# 4. Virtual Destructor

## Problem Without Virtual Destructor

Memory leak can occur when deleting derived object via base pointer.

---

## Program

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    virtual ~Base()
    {
        cout << "Base Destructor" << endl;
    }
};

class Derived : public Base
{
public:
    ~Derived()
    {
        cout << "Derived Destructor" << endl;
    }
};

int main()
{
    Base *ptr = new Derived();

    delete ptr;

    return 0;
}
```

---

## Output

```text
Derived Destructor
Base Destructor
```

---

# 5. Without Virtual Destructor (Wrong Behavior)

```cpp
class Base
{
public:
    ~Base()
    {
        cout << "Base Destructor" << endl;
    }
};
```

👉 Only Base destructor runs ❌  

👉 Derived cleanup skipped → memory leak risk

---

# How Virtual Works Internally?

## Uses:
👉 vtable (virtual table)  

👉 vptr (virtual pointer)

### Flow:
```
Object → vptr → vtable → function address
```

At runtime:
✔ Correct function is selected dynamically

# Memory Concept 

```
Base object:
+ vptr
+ data members

vtable:
[ Base::show ]
[ Derived::show ]
```

---

# Summary Table

| Feature | Virtual Function |
|--------|------------------|
| Binding | Runtime |
| Keyword | virtual |
| Purpose | Dynamic polymorphism |
| Used with | Base pointer/reference |
| Overridden in | Derived class |

---

# Real-Time Embedded Use Cases

| Area | Example |
|------|--------|
| HAL drivers | UART/SPI/I2C abstraction |
| Sensors | Different sensor implementations |
| RTOS | Task interface classes |
| Middleware | Logging / communication layers |

---

