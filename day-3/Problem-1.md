## DAY 3

### **Problem statement 3**

---

[**Problem link**](https://www.hackerrank.com/contests/day-3-of-30/challenges/find-me-1-6)

**Summary :** Check if the number of digits in `num` are even or not

**Solution 1:** You can count them digit by digit over the number.

**Solution 2:** From the start treat the number as string and based on the size you can determine is number is even or not.

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */
    string num;
    cin >> num;
    if (num.size() % 2 == 0) cout << "Even" << endl;
    else cout << "Odd" << endl;
    return 0;
}
```
