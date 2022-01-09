## DAY 5

### **Problem statement 2**

---

[**Problem link**](https://www.hackerrank.com/contests/day-5-of-30/challenges/set-union)

**Summary :** Given 2 array, count the all the unique elements after forming a union between two arrays.

**Solution :** A simple `set` data-structure will help here to maintain all the unique occurences of the array element

**Time Complexity :** Since there are `n` elements and `set` has `log(n)` insertion time, total time complexity would be `O(n * log(n))`

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
#include <set>
using namespace std;


int main() {
  int n, m;
  cin >> n >> m;
  set<int> s;

  for (int i = 0; i < n; i++) {
    int x;
    cin >> x;
    s.insert(x);
  }

  for (int i = 0; i < m; i++) {
    int x;
    cin >> x;
    s.insert(x);
  }

  cout << s.size() << endl;
  return 0;
}

```
