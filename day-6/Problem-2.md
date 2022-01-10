## DAY 6

### **Problem statement 2**

---

[**Problem link**](https://www.hackerrank.com/contests/day-6-of-30/challenges/largest-product-3)

**Summary :** Find the maximum product that can be achieved using any pair in the array.

**Solution :** Sort the elements in ascending order. Then take the `maximum(product-of-last-two-numbers, product-of-first-two-numbers)`;

**Time Complexity :** `O(n * log(n))`

**CPP Solution :**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
  int n;
  cin >> n;
  vector<int> arr(n);
  for (int i = 0; i < n; i++) cin >> arr[i];

  sort(arr.begin(), arr.end());
  int firstTwo = arr[0] * arr[1];
  int lastTwo = arr[n - 1] * arr[n - 2];
  cout << max(firstTwo, lastTwo) << endl;
  return 0;
}
```
