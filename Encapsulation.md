# C++ Encapsulation

## What is Encapsulation?

Encapsulation is the concept of **wrapping data and functions together into a single unit (class)** and **restricting direct access to data**.

👉 Achieved using:

- private data members
- public member functions (getters/setters)

# Why Encapsulation?

✔ Data hiding (security)  
✔ Controlled access  
✔ Better maintainability  
✔ Prevents accidental modification  

# 1. Basic Encapsulation Example

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
    // Setter functions
    void setData(int i, string n)
    {
        id = i;
        name = n;
    }

    // Getter functions
    void getData()
    {
        cout << "ID   : " << id << endl;
        cout << "Name : " << name << endl;
    }
};

int main()
{
    Student s1;

    s1.setData(101, "Prasanth");
    s1.getData();

    return 0;
}
```

---

## Output

```text
ID   : 101
Name : Prasanth
```

---

# 2. Encapsulation with Validation

## Program

```cpp
#include <iostream>
using namespace std;

class BankAccount
{
private:
    int balance;

public:
    void setBalance(int b)
    {
        if(b >= 0)
            balance = b;
        else
            balance = 0;
    }

    void deposit(int amount)
    {
        balance += amount;
    }

    void withdraw(int amount)
    {
        if(amount <= balance)
            balance -= amount;
        else
            cout << "Insufficient Balance" << endl;
    }

    void showBalance()
    {
        cout << "Balance = " << balance << endl;
    }
};

int main()
{
    BankAccount acc;

    acc.setBalance(1000);
    acc.deposit(500);
    acc.withdraw(300);
    acc.showBalance();

    return 0;
}
```

---

## Output

```text
Balance = 1200
```

---

# 3. Read-Only Encapsulation Example

## Program

```cpp
#include <iostream>
using namespace std;

class Employee
{
private:
    int id = 1001;

public:
    int getId()
    {
        return id;
    }
};

int main()
{
    Employee e;

    cout << "Employee ID = " << e.getId();

    return 0;
}
```

---

## Output

```text
Employee ID = 1001
```

---

# 4. Full Encapsulation (Real World Style)

## Program

```cpp
#include <iostream>
using namespace std;

class Sensor
{
private:
    int value;

public:
    void setValue(int v)
    {
        value = v;
    }

    int getValue()
    {
        return value;
    }

    void display()
    {
        cout << "Sensor Value = " << value << endl;
    }
};

int main()
{
    Sensor s;

    s.setValue(45);

    cout << s.getValue() << endl;
    s.display();

    return 0;
}
```

---

## Output

```text
45
Sensor Value = 45
```

---

# Encapsulation vs Data Hiding

| Concept | Meaning |
|--------|--------|
| Encapsulation | Wrapping data + methods in a class |
| Data Hiding | Restricting direct access to data |

👉 Encapsulation = structure  

👉 Data hiding = security layer  

---

# Real-Time Embedded Example

| Module | Encapsulation Use |
|--------|------------------|
| UART Driver | private registers, public APIs |
| Sensor module | hide raw ADC values |
| RTOS task | control access via functions |
| EEPROM driver | safe read/write APIs |

---

# Summary

👉 Encapsulation = data + methods + access control  

👉 Prevents direct data manipulation  

👉 Core principle of OOP used in real systems  

---

