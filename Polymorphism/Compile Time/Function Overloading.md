# C++ Function Overloading

## What is Function Overloading?

Function overloading means:

👉 Multiple functions having the **same name**

👉 But different **parameters (type, number, or order)**

It is an example of **Compile-Time Polymorphism**.

# Key Rules

- Same function name
- Different parameter list
- Return type alone is NOT enough for overloading

# 1. Basic Function Overloading Example

## Program

```cpp
#include <iostream>
using namespace std;

class Math
{
public:
    int add(int a, int b)
    {
        return a + b;
    }

    int add(int a, int b, int c)
    {
        return a + b + c;
    }

    float add(float a, float b)
    {
        return a + b;
    }
};

int main()
{
    Math obj;

    cout << "2 int sum   = " << obj.add(10, 20) << endl;
    cout << "3 int sum   = " << obj.add(10, 20, 30) << endl;
    cout << "float sum   = " << obj.add(2.5f, 3.5f) << endl;

    return 0;
}
```

---

## Output

```text
2 int sum   = 30
3 int sum   = 60
float sum   = 6
```

---

# 2. Overloading by Data Type

## Program

```cpp
#include <iostream>
using namespace std;

class Display
{
public:
    void show(int x)
    {
        cout << "Integer: " << x << endl;
    }

    void show(double x)
    {
        cout << "Double: " << x << endl;
    }

    void show(string x)
    {
        cout << "String: " << x << endl;
    }
};

int main()
{
    Display obj;

    obj.show(10);
    obj.show(3.14);
    obj.show("Embedded C++");

    return 0;
}
```

---

## Output

```text
Integer: 10
Double: 3.14
String: Embedded C++
```

---

# 3. Overloading by Number of Parameters

## Program

```cpp
#include <iostream>
using namespace std;

class Area
{
public:
    int calc(int a)
    {
        return a * a; // square
    }

    int calc(int l, int b)
    {
        return l * b; // rectangle
    }
};

int main()
{
    Area obj;

    cout << "Square Area   = " << obj.calc(5) << endl;
    cout << "Rectangle Area= " << obj.calc(4, 6) << endl;

    return 0;
}
```

---

## Output

```text
Square Area   = 25
Rectangle Area = 24
```

---

# 4. Invalid Overloading Example

## Program

```cpp
#include <iostream>
using namespace std;

class Test
{
public:
    int func(int a)
    {
        return a;
    }

    // ❌ Invalid: only return type is different
    // float func(int a)
    // {
    //     return a;
    // }
};

int main()
{
    Test obj;

    cout << obj.func(10);

    return 0;
}
```

## Why invalid?

👉 Function signature does NOT include return type  
👉 So compiler cannot distinguish

# Real-Time Embedded Example

Function overloading is used in firmware like:

| Use Case | Example |
|----------|--------|
| Sensor init | init(sensor_id) / init(sensor_id, mode) |
| UART config | uart_config(baud) / uart_config(baud, parity) |
| Logging | log(int) / log(float) / log(string) |

# Key Points

- Overloading improves code readability
- Avoids multiple function names
- Happens at compile time
- Very useful in drivers and HAL layers


# Summary

| Feature | Function Overloading |
|--------|----------------------|
| Type | Compile-time polymorphism |
| Same name | Yes |
| Parameters | Must differ |
| Return type | Not considered |

---
