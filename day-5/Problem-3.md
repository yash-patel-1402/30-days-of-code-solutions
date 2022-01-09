## DAY 5

### **Problem statement 3**

---

[**Problem link**](https://www.hackerrank.com/contests/day-5-of-30/challenges/compare-and-compile)

**Summary :** Check whether the `num` and its square have same last digit.

**Solution :** Just check `num % 10 == (num * num) % 10`

**Time Complexity :** Since there is only simple calculation, `O(1)`

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() {

  int n;
  cin >> n;
  int nn = n * n;
  if (nn % 10 == n % 10) {
    cout << "Phoenix number" << endl;
  }
  else {
    cout << "Not a phoenix number." << endl;
  }
    return 0;
}

```
