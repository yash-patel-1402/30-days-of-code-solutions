## DAY 6

### **Problem statement 1**

---

[**Problem link**](https://www.hackerrank.com/contests/day-6-of-30/challenges/find-the-younger-one)

**Summary :** For each index `i` in array, find the count of elements which are less `a[i]`

**Solution :** You could use nested loop to apply counters, means for each `a[i]` you will find all `a[j] < a[i]`. But applying sorting and using binary search for finding upper bound to a number will reduce complexity

**Time Complexity :** `O(n * log n)`

**CPP Solution :**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
  int n;
  cin >> n;
  vector<int> nums(n), sortedNums(n);

  for (int i = 0; i < n; i++) {
    int x;
    cin >> x;
    nums[i] = sortedNums[i] = x;
  }

  sort(sortedNums.begin(), sortedNums.end());

  vector<int> ans(n);
  for (int i = 0; i < n; i++) {
    ans[i] = distance(
      sortedNums.begin(),
      upper_bound(sortedNums.begin(), sortedNums.end(), nums[i] - 1)
    );
  }

  for (int i = 0; i < n; i++) cout << ans[i] << " ";
  return 0;
}

```
