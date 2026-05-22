# C++ Constructor and Destructor Examples

# 1. Constructor Example

## Program

```cpp
#include <iostream>
using namespace std;

class Student
{
private:
    int id;
    string name;

public:
    // Constructor
    Student()
    {
        id = 101;
        name = "Prasanth";

        cout << "Constructor Called" << endl;
    }

    void display()
    {
        cout << "ID   : " << id << endl;
        cout << "Name : " << name << endl;
    }
};

int main()
{
    Student s1;

    s1.display();

    return 0;
}
```

---

## Output

```text
Constructor Called
ID   : 101
Name : Prasanth
```

# What is Constructor?

A constructor is a special member function:
- Automatically called when object is created
- Used to initialize data members

## Constructor Rules

- Constructor name must be same as class name
- No return type
- Called automatically

```cpp
Student()
{
}
```

---

# 2. Parameterized Constructor Example

## Program

```cpp
#include <iostream>
using namespace std;

class Employee
{
private:
    int id;
    string name;

public:
    // Parameterized Constructor
    Employee(int i, string n)
    {
        id = i;
        name = n;
    }

    void display()
    {
        cout << "Employee ID   : " << id << endl;
        cout << "Employee Name : " << name << endl;
    }
};

int main()
{
    Employee e1(201, "Kumar");

    e1.display();

    return 0;
}
```

---

## Output

```text
Employee ID   : 201
Employee Name : Kumar
```

---

# 3. Constructor Overloading

## Program

```cpp
#include <iostream>
using namespace std;

class Demo
{
public:
    Demo()
    {
        cout << "Default Constructor" << endl;
    }

    Demo(int x)
    {
        cout << "Parameterized Constructor: " << x << endl;
    }
};

int main()
{
    Demo d1;

    Demo d2(100);

    return 0;
}
```

---

## Output

```text
Default Constructor
Parameterized Constructor: 100
```

---

# 4. Destructor Example

## Program

```cpp
#include <iostream>
using namespace std;

class Test
{
public:
    // Constructor
    Test()
    {
        cout << "Constructor Called" << endl;
    }

    // Destructor
    ~Test()
    {
        cout << "Destructor Called" << endl;
    }
};

int main()
{
    Test t1;

    return 0;
}
```

---

## Output

```text
Constructor Called
Destructor Called
```

---

# What is Destructor?

A destructor is a special member function:
- Automatically called when object is destroyed
- Used to release memory/resources

---

## Destructor Rules

- Same name as class
- Prefixed with `~`
- No return type
- No arguments

```cpp
~Test()
{
}
```

---

# 5. Constructor and Destructor Execution Order

## Program

```cpp
#include <iostream>
using namespace std;

class Demo
{
public:
    Demo()
    {
        cout << "Constructor Executed" << endl;
    }

    ~Demo()
    {
        cout << "Destructor Executed" << endl;
    }
};

int main()
{
    Demo d1;

    cout << "Inside Main Function" << endl;

    return 0;
}
```

---

## Output

```text
Constructor Executed
Inside Main Function
Destructor Executed
```

---

# Real-Time Analogy

```text
Constructor -> Opening a file
Destructor  -> Closing a file
```

---

# Types of Constructors

| Type | Description |
|---|---|
| Default Constructor | No arguments |
| Parameterized Constructor | Accepts arguments |
| Copy Constructor | Copies one object to another |

---

# Key Differences

| Constructor | Destructor |
|---|---|
| Initializes object | Destroys object |
| Called during object creation | Called during object destruction |
| Can be overloaded | Cannot be overloaded |
| No return type | No return type |

---

# Important Points

- Constructor reduces repetitive initialization code.
- Destructor prevents memory leaks.
- Constructor executes first.
- Destructor executes last.
- Useful in embedded systems for resource management.

---
