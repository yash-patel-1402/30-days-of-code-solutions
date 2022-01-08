## DAY 4

### **Problem statement 2**

---

[**Problem link**](https://www.hackerrank.com/contests/day-4-of-30/challenges/numbers-with-even-number-of-digits-1)

**Summary :** For all numbers in array, count total numbers who have even number of digits in them

**Solution :** You can use conventional method of extracting digit by digit and counting them. Since we don't have to do any operation with numbers here, we can use string directly and find its size.

**Time Complexity :** Since there is only 1 loop, it's time complexity is `O(n)`

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() {
  string num;
  int count = 0;

  int n;
  cin >> n;
  for (int i = 0; i < n; i++) {
    cin >> num;
    if (num.size() % 2 == 0) count++;
  }

  cout << count << endl;
  return 0;
}

```
