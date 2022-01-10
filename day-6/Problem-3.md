## DAY 6

### **Problem statement 3**

---

[**Problem link**](https://www.hackerrank.com/contests/day-6-of-30/challenges/story-of-n-and-k)

**Summary :** For each `k` consecutive elements find the largest sum.

**Solution :** First calculate the sum of first `k` numbers. Then take a loop from `k to n` and update the sum accordingly

**Time Complexity :** `O(n)`

**CPP Solution :**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
  int n, k;
  cin >> n >> k;
  vector<int> arr(n);

  for (int i = 0; i < n; i++) cin >> arr[i];

  int bestSum = 0, currentSum = 0;
  for (int i = 0; i < k; i++) currentSum += arr[i];

  for (int i = k; i < n; i++) {
    currentSum -= arr[i - k];
    currentSum += arr[i];
    bestSum = max(currentSum, bestSum);
  }

  cout << bestSum << endl;

  return 0;
}
```
