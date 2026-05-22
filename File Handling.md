# C++ File Handling Programs

## 1. Write Data to File

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ofstream fout("data.txt");

    fout << "Hello File Handling";

    fout.close();

    cout << "Data Written Successfully";

    return 0;
}
```

### Output

```text
Data Written Successfully
```

---

## 2. Read Data from File

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream fin("data.txt");

    string data;

    getline(fin, data);

    cout << data;

    fin.close();

    return 0;
}
```

### Output

```text
Hello File Handling
```

---

## 3. Append Data to File

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ofstream fout("data.txt", ios::app);

    fout << "\nAppending New Data";

    fout.close();

    cout << "Data Appended";

    return 0;
}
```

### Output

```text
Data Appended
```

---

## 4. Write Multiple Lines to File

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ofstream fout("multi.txt");

    fout << "Line 1" << endl;
    fout << "Line 2" << endl;
    fout << "Line 3";

    fout.close();

    cout << "Multiple Lines Written";

    return 0;
}
```

### Output

```text
Multiple Lines Written
```

---

## 5. Read File Line by Line

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream fin("multi.txt");

    string line;

    while(getline(fin, line)) {
        cout << line << endl;
    }

    fin.close();

    return 0;
}
```

### Output

```text
Line 1
Line 2
Line 3
```

---

## 6. Count Characters in File

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream fin("data.txt");

    char ch;
    int count = 0;

    while(fin.get(ch)) {
        count++;
    }

    cout << "Characters: " << count;

    fin.close();

    return 0;
}
```

### Output

```text
Characters: 35
```

---

## 7. Count Words in File

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream fin("data.txt");

    string word;
    int count = 0;

    while(fin >> word) {
        count++;
    }

    cout << "Words: " << count;

    fin.close();

    return 0;
}
```

### Output

```text
Words: 5
```

---

## 8. Copy One File to Another

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream fin("data.txt");
    ofstream fout("copy.txt");

    string line;

    while(getline(fin, line)) {
        fout << line << endl;
    }

    cout << "File Copied";

    fin.close();
    fout.close();

    return 0;
}
```

### Output

```text
File Copied
```

---

## 9. Student Record Write

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

struct Student {
    int id;
    char name[20];
};

int main() {
    Student s = {101, "Prasanth"};

    ofstream fout("student.txt");

    fout << s.id << " " << s.name;

    fout.close();

    cout << "Student Record Saved";

    return 0;
}
```

### Output

```text
Student Record Saved
```

---

## 10. Student Record Read

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream fin("student.txt");

    int id;
    string name;

    fin >> id >> name;

    cout << "ID: " << id << endl;
    cout << "Name: " << name;

    fin.close();

    return 0;
}
```

### Output

```text
ID: 101
Name: Prasanth
```

---

## 11. Binary File Write

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

struct Data {
    int num;
};

int main() {
    Data d = {100};

    ofstream fout("binary.dat", ios::binary);

    fout.write((char*)&d, sizeof(d));

    fout.close();

    cout << "Binary Data Written";

    return 0;
}
```

### Output

```text
Binary Data Written
```

---

## 12. Binary File Read

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

struct Data {
    int num;
};

int main() {
    Data d;

    ifstream fin("binary.dat", ios::binary);

    fin.read((char*)&d, sizeof(d));

    cout << "Number: " << d.num;

    fin.close();

    return 0;
}
```

### Output

```text
Number: 100
```

---

## 13. File Pointer Position

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ofstream fout("demo.txt");

    fout << "Hello";

    cout << "Position: " << fout.tellp();

    fout.close();

    return 0;
}
```

### Output

```text
Position: 5
```

---

## 14. Random Access in File

### Program

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    fstream file("demo.txt", ios::in);

    file.seekg(2);

    char ch;

    file.get(ch);

    cout << ch;

    file.close();

    return 0;
}
```

### Output

```text
l
```

---

## 15. Delete File

### Program

```cpp
#include <iostream>
#include <cstdio>
using namespace std;

int main() {
    remove("demo.txt");

    cout << "File Deleted";

    return 0;
}
```

### Output

```text
File Deleted
```

---
