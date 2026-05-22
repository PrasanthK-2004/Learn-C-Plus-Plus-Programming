# C++ STL Programs

## 1. Vector Example

### Program

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v = {10, 20, 30, 40};

    for(int i : v)
        cout << i << " ";

    return 0;
}
```

### Output

```text
10 20 30 40
```

---

## 2. Vector Push and Pop

### Program

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v;

    v.push_back(10);
    v.push_back(20);
    v.push_back(30);

    v.pop_back();

    for(int i : v)
        cout << i << " ";

    return 0;
}
```

### Output

```text
10 20
```

---

## 3. List Example

### Program

```cpp
#include <iostream>
#include <list>
using namespace std;

int main() {
    list<int> l = {1,2,3,4};

    for(int i : l)
        cout << i << " ";

    return 0;
}
```

### Output

```text
1 2 3 4
```

---

## 4. Stack Example

### Program

```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    stack<int> s;

    s.push(10);
    s.push(20);
    s.push(30);

    cout << "Top Element: " << s.top();

    return 0;
}
```

### Output

```text
Top Element: 30
```

---

## 5. Queue Example

### Program

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;

    q.push(10);
    q.push(20);
    q.push(30);

    cout << "Front Element: " << q.front();

    return 0;
}
```

### Output

```text
Front Element: 10
```

---

## 6. Priority Queue Example

### Program

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    priority_queue<int> pq;

    pq.push(10);
    pq.push(50);
    pq.push(20);

    cout << "Largest Element: " << pq.top();

    return 0;
}
```

### Output

```text
Largest Element: 50
```

---

## 7. Set Example

### Program

```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
    set<int> s = {5,2,8,1,5};

    for(int i : s)
        cout << i << " ";

    return 0;
}
```

### Output

```text
1 2 5 8
```

---

## 8. Multiset Example

### Program

```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
    multiset<int> ms = {1,1,2,3,3};

    for(int i : ms)
        cout << i << " ";

    return 0;
}
```

### Output

```text
1 1 2 3 3
```

---

## 9. Map Example

### Program

```cpp
#include <iostream>
#include <map>
using namespace std;

int main() {
    map<int,string> m;

    m[1] = "Prasanth";
    m[2] = "Kumar";

    for(auto i : m)
        cout << i.first << " " << i.second << endl;

    return 0;
}
```

### Output

```text
1 Prasanth
2 Kumar
```

---

## 10. Unordered Map Example

### Program

```cpp
#include <iostream>
#include <unordered_map>
using namespace std;

int main() {
    unordered_map<int,string> um;

    um[1] = "C";
    um[2] = "C++";

    for(auto i : um)
        cout << i.first << " " << i.second << endl;

    return 0;
}
```

### Output

```text
2 C++
1 C
```

---

## 11. Pair Example

### Program

```cpp
#include <iostream>
using namespace std;

int main() {
    pair<int,string> p;

    p.first = 101;
    p.second = "Embedded";

    cout << p.first << " " << p.second;

    return 0;
}
```

### Output

```text
101 Embedded
```

---

## 12. Deque Example

### Program

```cpp
#include <iostream>
#include <deque>
using namespace std;

int main() {
    deque<int> d;

    d.push_front(10);
    d.push_back(20);
    d.push_back(30);

    for(int i : d)
        cout << i << " ";

    return 0;
}
```

### Output

```text
10 20 30
```

---

## 13. Sort Function Example

### Program

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int arr[] = {5,2,8,1};

    sort(arr, arr+4);

    for(int i=0; i<4; i++)
        cout << arr[i] << " ";

    return 0;
}
```

### Output

```text
1 2 5 8
```

---

## 14. Binary Search Example

### Program

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int arr[] = {1,2,3,4,5};

    if(binary_search(arr, arr+5, 3))
        cout << "Element Found";
    else
        cout << "Element Not Found";

    return 0;
}
```

### Output

```text
Element Found
```

---

## 15. Reverse Function Example

### Program

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int arr[] = {1,2,3,4,5};

    reverse(arr, arr+5);

    for(int i=0; i<5; i++)
        cout << arr[i] << " ";

    return 0;
}
```

### Output

```text
5 4 3 2 1
```

---

## 16. Max and Min Element Example

### Program

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int arr[] = {10,40,5,90,20};

    cout << "Max: " << *max_element(arr, arr+5) << endl;
    cout << "Min: " << *min_element(arr, arr+5);

    return 0;
}
```

### Output

```text
Max: 90
Min: 5
```

---

## 17. Count Function Example

### Program

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int arr[] = {1,2,2,3,2};

    cout << count(arr, arr+5, 2);

    return 0;
}
```

### Output

```text
3
```

---

## 18. String STL Example

### Program

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string str = "Embedded";

    cout << "Length: " << str.length();

    return 0;
}
```

### Output

```text
Length: 8
```

---

## 19. Iterator Example

### Program

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v = {10,20,30};

    vector<int>::iterator it;

    for(it = v.begin(); it != v.end(); it++)
        cout << *it << " ";

    return 0;
}
```

### Output

```text
10 20 30
```

---

## 20. Lambda Function Example

### Program

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int arr[] = {1,2,3,4,5};

    int countEven = count_if(arr, arr+5,
                    [](int x) {
                        return x % 2 == 0;
                    });

    cout << "Even Count: " << countEven;

    return 0;
}
```

### Output

```text
Even Count: 2
```

---
