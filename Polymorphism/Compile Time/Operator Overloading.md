# C++ Operator Overloading

## What is Operator Overloading?

Operator overloading allows you to redefine operators (`+`, `-`, `*`, etc.) for user-defined classes.

👉 It is a form of **Compile-Time Polymorphism**


# Rules of Operator Overloading

- At least one operand must be a user-defined type
- Cannot change operator precedence
- Cannot create new operators
- Some operators cannot be overloaded

# 1. Unary Operator Overloading (++)

## Pre-Increment Program

```cpp
#include <iostream>
using namespace std;

class Counter
{
private:
    int count;

public:
    Counter()
    {
        count = 0;
    }

    void operator++()
    {
        ++count;
    }

    void display()
    {
        cout << "Count = " << count << endl;
    }
};

int main()
{
    Counter c;

    ++c;
    ++c;

    c.display();

    return 0;
}
```

## Output

```text
Count = 2
```

---
## Post-Increment Program

```cpp
#include <iostream>
using namespace std;

class Counter
{
private:
    int count;

public:
    Counter()
    {
        count = 0;
    }

    void operator++(int)
    {
        count++;
    }

    void display()
    {
        cout << "Count = " << count << endl;
    }
};

int main()
{
    Counter c;

    c++;

    c.display();

    return 0;
}
```

## Output

```text
Count = 1
```

---

# 2. Binary Operator Overloading (+)

## Program

```cpp
#include <iostream>
using namespace std;

class Complex
{
private:
    int real, imag;

public:
    Complex(int r = 0, int i = 0)
    {
        real = r;
        imag = i;
    }

    Complex operator + (Complex obj)
    {
        Complex temp;

        temp.real = real + obj.real;
        temp.imag = imag + obj.imag;

        return temp;
    }

    void display()
    {
        cout << real << " + i" << imag << endl;
    }
};

int main()
{
    Complex c1(10, 5), c2(3, 7);

    Complex c3 = c1 + c2;

    c3.display();

    return 0;
}
```

## Output

```text
13 + i12
```

---

# 3. Subtraction Operator (-)

## Program

```cpp
#include <iostream>
using namespace std;

class Complex
{
private:
    int real, imag;

public:
    Complex(int r = 0, int i = 0)
    {
        real = r;
        imag = i;
    }

    Complex operator - (Complex obj)
    {
        Complex temp;

        temp.real = real - obj.real;
        temp.imag = imag - obj.imag;

        return temp;
    }

    void display()
    {
        cout << real << " + i" << imag << endl;
    }
};

int main()
{
    Complex c1(20, 10), c2(5, 3);

    Complex c3 = c1 - c2;

    c3.display();

    return 0;
}
```

## Output

```text
15 + i7
```

---

# 4. Multiplication Operator (*)

## Program

```cpp
#include <iostream>
using namespace std;

class Complex
{
private:
    int real, imag;

public:
    Complex(int r = 1, int i = 1)
    {
        real = r;
        imag = i;
    }

    Complex operator * (Complex obj)
    {
        Complex temp;

        temp.real = real * obj.real;
        temp.imag = imag * obj.imag;

        return temp;
    }

    void display()
    {
        cout << real << " + i" << imag << endl;
    }
};

int main()
{
    Complex c1(2, 3), c2(4, 5);

    Complex c3 = c1 * c2;

    c3.display();

    return 0;
}
```

## Output

```text
8 + i15
```

---

# 5. Division Operator (/)

## Program

```cpp
#include <iostream>
using namespace std;

class Number
{
private:
    int value;

public:
    Number(int v = 1)
    {
        value = v;
    }

    Number operator / (Number obj)
    {
        Number temp;

        temp.value = value / obj.value;

        return temp;
    }

    void display()
    {
        cout << "Value = " << value << endl;
    }
};

int main()
{
    Number n1(20), n2(5);

    Number n3 = n1 / n2;

    n3.display();

    return 0;
}
```

## Output

```text
Value = 4
```

---

# 6. Relational Operator (==)

## Program

```cpp
#include <iostream>
using namespace std;

class Number
{
private:
    int value;

public:
    Number(int v)
    {
        value = v;
    }

    bool operator == (Number obj)
    {
        return value == obj.value;
    }
};

int main()
{
    Number n1(10), n2(10);

    if(n1 == n2)
        cout << "Equal";
    else
        cout << "Not Equal";

    return 0;
}
```

## Output

```text
Equal
```

---

# 7. Relational Operator (!=)

## Program

```cpp
#include <iostream>
using namespace std;

class Number
{
private:
    int value;

public:
    Number(int v)
    {
        value = v;
    }

    bool operator != (Number obj)
    {
        return value != obj.value;
    }
};

int main()
{
    Number n1(10), n2(20);

    if(n1 != n2)
        cout << "Not Equal";
    else
        cout << "Equal";

    return 0;
}
```

## Output

```text
Not Equal
```

---

# 8. Assignment Operator (=)

## Program

```cpp
#include <iostream>
using namespace std;

class Number
{
private:
    int value;

public:
    Number(int v = 0)
    {
        value = v;
    }

    void operator = (const Number &obj)
    {
        value = obj.value;
    }

    void display()
    {
        cout << "Value = " << value << endl;
    }
};

int main()
{
    Number n1(50), n2;

    n2 = n1;

    n2.display();

    return 0;
}
```

## Output

```text
Value = 50
```

---

# 9. Subscript Operator ([])

## Program

```cpp
#include <iostream>
using namespace std;

class Array
{
private:
    int arr[5];

public:
    Array()
    {
        for(int i = 0; i < 5; i++)
            arr[i] = i * 10;
    }

    int operator[](int index)
    {
        return arr[index];
    }
};

int main()
{
    Array a;

    cout << a[2];

    return 0;
}
```

## Output

```text
20
```

---

# 10. Function Call Operator (())

## Program

```cpp
#include <iostream>
using namespace std;

class Functor
{
public:
    void operator()()
    {
        cout << "Function Call Operator" << endl;
    }
};

int main()
{
    Functor f;

    f();

    return 0;
}
```

## Output

```text
Function Call Operator
```

---

# 11. Stream Insertion Operator (<<)

## Program

```cpp
#include <iostream>
using namespace std;

class Student
{
private:
    int id;

public:
    Student(int i)
    {
        id = i;
    }

    friend ostream& operator << (ostream &out, Student s)
    {
        out << "ID = " << s.id;

        return out;
    }
};

int main()
{
    Student s(101);

    cout << s;

    return 0;
}
```

## Output

```text
ID = 101
```

---

# 12. Stream Extraction Operator (>>)

## Program

```cpp
#include <iostream>
using namespace std;

class Student
{
private:
    int id;

public:
    friend istream& operator >> (istream &in, Student &s)
    {
        in >> s.id;

        return in;
    }

    void display()
    {
        cout << "ID = " << id << endl;
    }
};

int main()
{
    Student s;

    cout << "Enter ID: ";
    cin >> s;

    s.display();

    return 0;
}
```

## Output

```text
Enter ID: 101
ID = 101
```

---

# Operators That Cannot Be Overloaded

| Operator | Reason |
|----------|---------|
| `.` | Class member selector Operator |
| `::` | Scope Resolution Operator |
| `?:` | Ternary operator |
| `sizeof` | Size of Operator |
| `typeid` | Object type Operator |
| `.*` | Member pointer selector Operator |

---

# Real-Time Embedded Use Cases

| Operator | Embedded Usage |
|----------|----------------|
| `+ - * /` | Sensor calculations |
| `== !=` | Register comparison |
| `[]` | Memory-mapped registers |
| `()` | Driver APIs |
| `<< >>` | UART debug logging |

---





 
