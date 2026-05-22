# C++ Basic Syntax (Complete Beginner Notes)

---

# 1. Simple C++ Program Structure

```cpp
#include <iostream>
using namespace std;

int main()
{
    cout << "Hello World";
    return 0;
}
```

## Output
```
Hello World
```

---

# Explanation

### 1. Header File
```cpp
#include <iostream>
```
Used for input/output operations (`cin`, `cout`).

### 2. Namespace
```cpp
using namespace std;
```
Avoids writing `std::cout`, `std::cin` every time.

### 3. Main Function
```cpp
int main()
```
Execution starts from here.

### 4. Output Statement
```cpp
cout << "Hello World";
```
Used to print output.

### 5. Return Statement
```cpp
return 0;
```
Indicates successful program execution.

---

# 2. Input and Output Example

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a;

    cout << "Enter a number: ";
    cin >> a;

    cout << "You entered: " << a;

    return 0;
}
```

## Output
```
Enter a number: 5
You entered: 5
```

---

# 3. Data Types Example

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a = 10;
    float b = 3.5;
    char c = 'A';
    double d = 9.99;

    cout << a << endl;
    cout << b << endl;
    cout << c << endl;
    cout << d << endl;

    return 0;
}
```

## Output
```
10
3.5
A
9.99
```

---

# 4. Variables

```cpp
int x = 5;
float y = 2.5;
char z = 'B';
```

## Output
```
x = 5
y = 2.5
z = B
```

---

# 5. Operators Example

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a = 10, b = 5;

    cout << "Sum = " << (a + b) << endl;
    cout << "Sub = " << (a - b) << endl;
    cout << "Mul = " << (a * b) << endl;
    cout << "Div = " << (a / b) << endl;

    return 0;
}
```

## Output
```
Sum = 15
Sub = 5
Mul = 50
Div = 2
```

---

# 6. Conditional Statement (if-else)

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a = 10;

    if(a > 0)
        cout << "Positive Number";
    else
        cout << "Negative Number";

    return 0;
}
```

## Output
```
Positive Number
```

---

# 7. Loop Example (for loop)

```cpp
#include <iostream>
using namespace std;

int main()
{
    for(int i = 0; i < 5; i++)
    {
        cout << i << endl;
    }

    return 0;
}
```

## Output
```
0
1
2
3
4
```

---

# 8. While Loop

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i = 0;

    while(i < 5)
    {
        cout << i << endl;
        i++;
    }

    return 0;
}
```

## Output
```
0
1
2
3
4
```

---

# 9. Do-While Loop

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i = 0;

    do
    {
        cout << i << endl;
        i++;
    }
    while(i < 5);

    return 0;
}
```

## Output
```
0
1
2
3
4
```

---

# 10. Function Example

```cpp
#include <iostream>
using namespace std;

void display()
{
    cout << "Hello Function";
}

int main()
{
    display();
    return 0;
}
```

## Output
```
Hello Function
```

---

# 11. Array Example

```cpp
#include <iostream>
using namespace std;

int main()
{
    int arr[3] = {10, 20, 30};

    for(int i = 0; i < 3; i++)
    {
        cout << arr[i] << endl;
    }

    return 0;
}
```

## Output
```
10
20
30
```

---

# 12. Class Example (Basic OOP)

```cpp
#include <iostream>
using namespace std;

class Demo
{
public:
    void show()
    {
        cout << "Class Example";
    }
};

int main()
{
    Demo obj;
    obj.show();

    return 0;
}
```

## Output
```
Class Example
```

---

# Key Points

- C++ is case-sensitive
- Execution starts from `main()`
- `{}` defines block scope
- `;` ends every statement
- `cout` → output
- `cin` → input

---

# Summary

| Topic | Purpose |
|---|---|
| `#include<iostream>` | Header for input/output |
| `main()` | Starting point of program |
| `cout` | Print output |
| `cin` | Take input |
| Variables | Store data |
| Operators | Perform calculations |
| Loops | Repeat execution |
| Functions | Reusable code |
| Arrays | Store multiple values |
| Classes | OOP concept |

---
