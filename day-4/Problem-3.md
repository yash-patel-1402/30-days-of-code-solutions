## DAY 4

### **Problem statement 3**

---

[**Problem link**](https://www.hackerrank.com/contests/day-4-of-30/challenges/triplets-summing-to-zero)

**Summary :** For each possible triplets in the array, find whether any triplet has sum of 0.

**Solution 1:** Since maximum value of `n` is 104 we can use solution whose time complexity is of `O(n^3)` since 100^3 is about 10e6 and it can execute under given time constraints. So such solution would be brute force using nested loops for iterating over each triplets and getting their sum.

**Time Complexity 1:** Since there will be nesting of 3 loops, time complexity is `O(n^3)`

**CPP Solution 1:**

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

  int arr[n];
  for (int i = 0; i < n; i++) cin >> arr[i];

  for (int first = 0; first < n - 2; first++) {
    for (int second = first + 1; second < n - 1; second++) {
      for (int third = second + 1; third < n; third++) {
        int sum = arr[first] + arr[second] + arr[third];
        if (sum == 0) {
          cout << "true" << endl;
          return 0;
        }
      }
    }
  }

  cout << "false" << endl;
  return 0;
}
```

**Solution 2:** If we maintain a map of occureneces of each elements, we can iterate over each pair and based on the `partialSum` of the pair, we can get whatever `requiredNum` is required for generating sum of 0. We can look up on the map for the `requiredNum` and conclude if there is 0-sum possible or not

**Time Complexity 2:**

**CPP Solution 2:**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <unordered_map>
#include <algorithm>
using namespace std;


int main() {
  int n;
  cin >> n;
  vector<int> v(n);
  for (auto &i: v) cin >> i;

  unordered_map<int, int> mp;
  for (auto i: v) mp[i]++;

  for (int first = 0; first < n - 1; first++) {
    for (int second = first + 1; j < n; j++) {
      int partialSum = v[first] + v[second];
      int reqNum = 0 - partialSum;

      // how many reqNum are required
      int requiredCount = 1;
      if (v[i] == reqNum) requiredCount++;
      if (v[second] == reqNum) requiredCount++;

      if (mp[reqNum] >= requiredCount) {
        cout << "true" << endl;
        return 0;
      }
    }
  }

  cout << "false" << endl;
  return 0;
}

```
