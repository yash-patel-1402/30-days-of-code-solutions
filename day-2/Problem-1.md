## DAY 2

### **Problem statement 1**

---

[**Problem link**] (https://www.hackerrank.com/contests/day-2-of-30/challenges/lucky-number-23)

**Summary :** Given a number `num`, check if all the digits are unique. If unique then output `The number is lucky.` else output `The number is unlucky.`.

**Solution 1:**

This is a typical use-case of a **set** data-structure. One by one insert the digit into the set and the moment you find element that is already in the set, conclude your output.

**Time Complexity :**

Since we are using set, set requires `log(n)` for insertion and since there can be total `n` insertion, total time complexity `O(n log n)` where `n` is the number of digits in the `num`

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <set>
#include <algorithm>
using namespace std;


int main() {
  string num;
  set<int> s;

  cin >> num;
  for (auto digit: num) {
    if (s.find(digit) != s.end()) {
      // digit is already in the set
      cout << "The number is unlucky." << endl;
      return 0;
    }
    s.insert(digit);
  }

  cout << "The number is lucky." << endl;
  return 0;
}
```

**Solution 2:**
Since this problem is using only digits (0-9), you can also use counting array that stores counts of the character. This way you will eliminate the time required by the set to insert and maintain itself.
Although this may not increase the efficiency for this current constraints of the problem, it would be helpful when the number of digits in `num` are large.

**Time Complexity :**

Since we are using count array, we can access any count in `O(1)` time, so total complexity would be `O(n)` since we are doing atmost `n` iterations over the number.

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <set>
#include <algorithm>
using namespace std;


int main() {
  string num;
  int counts[10] = {0};

  cin >> num;
  for (auto digit: num) {
    counts[digit - '0']++;
    if (counts[digit - '0'] > 1) {
      // there are more than 1 occurences of the same digit
      cout << "The number is unlucky." << endl;
      return 0;
    }
  }

  cout << "The number is lucky." << endl;
  return 0;
}
```
