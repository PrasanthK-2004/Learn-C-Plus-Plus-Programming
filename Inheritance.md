# C++ Inheritance (All Types with Examples)

Inheritance is an OOP feature where a **child class (derived class)** acquires properties and behavior of a **parent class (base class)**.

# 1. Single Inheritance
One derived class inherits from one base class.

## Program

```cpp
#include <iostream>
using namespace std;

class A
{
public:
    void showA()
    {
        cout << "Class A function" << endl;
    }
};

class B : public A
{
public:
    void showB()
    {
        cout << "Class B function" << endl;
    }
};

int main()
{
    B obj;

    obj.showA();
    obj.showB();

    return 0;
}
```

## Output

```text
Class A function
Class B function
```

---

# 2. Multilevel Inheritance
A class is derived from another derived class.

## Program

```cpp
#include <iostream>
using namespace std;

class A
{
public:
    void showA()
    {
        cout << "Class A" << endl;
    }
};

class B : public A
{
public:
    void showB()
    {
        cout << "Class B" << endl;
    }
};

class C : public B
{
public:
    void showC()
    {
        cout << "Class C" << endl;
    }
};

int main()
{
    C obj;

    obj.showA();
    obj.showB();
    obj.showC();

    return 0;
}
```

## Output

```text
Class A
Class B
Class C
```

---

# 3. Multiple Inheritance
One class inherits from multiple base classes.

## Program

```cpp
#include <iostream>
using namespace std;

class A
{
public:
    void showA()
    {
        cout << "Class A" << endl;
    }
};

class B
{
public:
    void showB()
    {
        cout << "Class B" << endl;
    }
};

class C : public A, public B
{
public:
    void showC()
    {
        cout << "Class C" << endl;
    }
};

int main()
{
    C obj;

    obj.showA();
    obj.showB();
    obj.showC();

    return 0;
}
```

## Output

```text
Class A
Class B
Class C
```

---

# 4. Hierarchical Inheritance
Multiple derived classes inherit from one base class.

## Program

```cpp
#include <iostream>
using namespace std;

class A
{
public:
    void showA()
    {
        cout << "Class A" << endl;
    }
};

class B : public A
{
public:
    void showB()
    {
        cout << "Class B" << endl;
    }
};

class C : public A
{
public:
    void showC()
    {
        cout << "Class C" << endl;
    }
};

int main()
{
    B obj1;
    C obj2;

    obj1.showA();
    obj1.showB();

    obj2.showA();
    obj2.showC();

    return 0;
}
```

## Output

```text
Class A
Class B
Class A
Class C
```

---

# 5. Hybrid Inheritance
Combination of two or more types of inheritance.

## Program (Diamond Problem Example)

```cpp
#include <iostream>
using namespace std;

class A
{
public:
    void showA()
    {
        cout << "Class A" << endl;
    }
};

class B : virtual public A
{
};

class C : virtual public A
{
};

class D : public B, public C
{
};

int main()
{
    D obj;

    obj.showA();

    return 0;
}
```

## Output

```text
Class A
```

---

# Why Virtual Inheritance?

Without `virtual`, Diamond Problem occurs:

```text
    A
   / \
  B   C
   \ /
    D
```

- D gets two copies of A ❌
- Virtual inheritance ensures single copy ✔

---

# Summary Table

| Type | Description |
|------|------------|
| Single | 1 base → 1 derived |
| Multilevel | chain inheritance |
| Multiple | many base → 1 derived |
| Hierarchical | 1 base → many derived |
| Hybrid | combination of above |

---

# Real-Time Embedded Example

| Inheritance Type | Embedded Example |
|------------------|-----------------|
| Single | GPIO driver → LED driver |
| Multilevel | Peripheral → UART → Debug UART |
| Multiple | Sensor + Communication → IoT module |
| Hierarchical | Base driver → multiple sensors |
| Hybrid | RTOS task + hardware abstraction layer |

---
