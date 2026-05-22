# C++ Pointer Programs

## 1. Basic Pointer Example

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    int *p = &a;

    cout << "Value of a: " << a << endl;
    cout << "Address of a: " << p << endl;
    cout << "Value using pointer: " << *p << endl;

    return 0;
}
```

### Output

```text
Value of a: 10
Address of a: 0x61ff08
Value using pointer: 10
```

---

## 2. Swap Two Numbers Using Pointers

### Program

```cpp
#include <iostream>
using namespace std;

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 5, y = 10;

    swap(&x, &y);

    cout << "x = " << x << endl;
    cout << "y = " << y << endl;

    return 0;
}
```

### Output

```text
x = 10
y = 5
```

---

## 3. Pointer Arithmetic

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10,20,30};

    int *p = arr;

    cout << *p << endl;

    p++;

    cout << *p << endl;

    return 0;
}
```

### Output

```text
10
20
```

---

## 4. Sum of Array Using Pointers

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {1,2,3,4,5};

    int *p = arr;
    int sum = 0;

    for(int i = 0; i < 5; i++) {
        sum += *(p + i);
    }

    cout << "Sum = " << sum;

    return 0;
}
```

### Output

```text
Sum = 15
```

---

## 5. Find Largest Element Using Pointer

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {5,8,2,15,9};

    int *p = arr;
    int max = *p;

    for(int i = 1; i < 5; i++) {
        if(*(p + i) > max)
            max = *(p + i);
    }

    cout << "Largest = " << max;

    return 0;
}
```

### Output

```text
Largest = 15
```

---

## 6. Dynamic Memory Allocation

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int *p = new int;

    *p = 100;

    cout << "Value = " << *p;

    delete p;

    return 0;
}
```

### Output

```text
Value = 100
```

---

## 7. Pointer to Pointer

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10;

    int *p = &a;
    int **q = &p;

    cout << "a = " << a << endl;
    cout << "*p = " << *p << endl;
    cout << "**q = " << **q << endl;

    return 0;
}
```

### Output

```text
a = 10
*p = 10
**q = 10
```

---

## 8. Function Returning Pointer

### Program

```cpp
#include <iostream>
using namespace std;

int* getValue() {
    static int x = 50;
    return &x;
}

int main() {
    int *p = getValue();

    cout << *p;

    return 0;
}
```

### Output

```text
50
```

---

## 9. Traversing String Using Pointer

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    char str[] = "HELLO";

    char *p = str;

    while(*p != '\0') {
        cout << *p << " ";
        p++;
    }

    return 0;
}
```

### Output

```text
H E L L O
```

---

## 10. Reverse Array Using Pointers

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {1,2,3,4,5};

    int *start = arr;
    int *end = arr + 4;

    while(start < end) {
        int temp = *start;
        *start = *end;
        *end = temp;

        start++;
        end--;
    }

    for(int i = 0; i < 5; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

### Output

```text
5 4 3 2 1
```

---

## 11. Pointer with Structures

### Program

```cpp
#include <iostream>
using namespace std;

struct Student {
    int id;
};

int main() {
    Student s = {101};

    Student *p = &s;

    cout << "ID = " << p->id;

    return 0;
}
```

### Output

```text
ID = 101
```

---

## 12. Array of Pointers

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 20, c = 30;

    int *arr[] = {&a, &b, &c};

    for(int i = 0; i < 3; i++) {
        cout << *arr[i] << " ";
    }

    return 0;
}
```

### Output

```text
10 20 30
```

---

## 13. Void Pointer Example

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 25;

    void *p = &a;

    cout << *(int*)p;

    return 0;
}
```

### Output

```text
25
```

---

## 14. Pointer to Function

### Program

```cpp
#include <iostream>
using namespace std;

void display() {
    cout << "Function Pointer";
}

int main() {
    void (*fp)();

    fp = display;

    fp();

    return 0;
}
```

### Output

```text
Function Pointer
```

---

## 15. Dangling Pointer Example

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    int *p = new int(10);

    delete p;

    p = NULL;

    if(p == NULL)
        cout << "Pointer is NULL";

    return 0;
}
```

### Output

```text
Pointer is NULL
```

---
