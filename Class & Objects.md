# C++ Class and Object Example

## Program

```cpp
#include <iostream>
using namespace std;

// Class Definition
class Student
{
private:
    int id;
    string name;

public:
    // Member Function to set data
    void setData(int i, string n)
    {
        id = i;
        name = n;
    }

    // Member Function to display data
    void display()
    {
        cout << "Student ID   : " << id << endl;
        cout << "Student Name : " << name << endl;
    }
};

int main()
{
    // Object Creation
    Student s1;

    // Calling Member Functions
    s1.setData(101, "Prasanth");

    s1.display();

    return 0;
}
```

---

## Output

```text
Student ID   : 101
Student Name : Prasanth
```

# Explanation

## Class
A class is a user-defined data type that contains:
- Data members (variables)
- Member functions (functions)

```cpp
class Student
```

## Object
An object is an instance of a class.

```cpp
Student s1;
```

## Access Specifiers

### private
Accessible only inside the class.

```cpp
private:
    int id;
```

### public
Accessible outside the class using object.

```cpp
public:
    void display();
```

## Member Functions

### setData()
Used to assign values.

### display()
Used to print values.

# Real-Time Analogy

```text
Class  -> Blueprint
Object -> Real Product
```

Example:
```text
Class  = Car
Objects = BMW, Audi, Tesla
```

---

# Key Points

- Class does not occupy memory until object is created.
- Objects access class members using dot operator.
- Encapsulation is achieved using classes.
- Classes improve code reusability and modularity.

---
