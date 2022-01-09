## DAY 5

### **Problem statement 1**

---

[**Problem link**](https://www.hackerrank.com/contests/day-5-of-30/challenges/line-of-people-1)

**Summary :** There are atleast `a` people in front and atmost `b` people in behind. Calculate possible positions if the total number of people in line are `n`

**Solution :** Since there are `a` people in front, all the possible position starts from `a+1, a+2, .... n`. Now since there are atmost `b` people behind so another possible sequence for this would be `n-b-1, n-b, n-b+1, n-b+2, ... n`. So combining both sequences, we should only take positions that are in both sequences.

eg., `n = 8`, `a = 2`, `b = 4`

So correct sequence for `a` would be `[3, 4, 5, 6, 7, 8]`

Correct sequence for `b` would be `[4, 5, 6, 7, 8]`, we can't add `[1, 2, 3]` because adding any of that would result into `more than b` people at the behind.

So now final sequence would be the common positions between them, so `[4, 5, 6, 7, 8]` is the answer.

Alternatively, `n - max(a, n-b-1)` is the answer.

In short calculate `b - max(a, n - b - 1)`

**Time Complexity :** Since there are only simple calculations, it's time complexity is `O(1)`

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() {
  int n, a ,b;
  cin >> n >> a >> b;
  b = n - b - 1;
  cout << n - max(a, b) << endl;
  return 0;
}
```
