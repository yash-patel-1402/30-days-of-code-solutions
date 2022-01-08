## DAY 4

### **Problem statement 1**

---

[**Problem link**](https://www.hackerrank.com/contests/day-4-of-30/challenges/playing-with-arrays-1-1)

**Summary :** for each position `i` in array, get the sum from `arr[0], arr[1], ..., arr[i]`

**Solution :** Iterate through the array and update the value with sum of previous value and current value.

**Time Complexity :** Since there is only 1 loop to iterate over, time complexity is `O(n)`

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
  int arr[n];
  for (int i = 0; i < n; i++) cin >> arr[i];

  for (int i = 1; i < n; i++) arr[i] = arr[i] + arr[i - 1];

  for (int i = 0; i < n; i++) cout << arr[i] << " ";
  cout << endl;
  return 0;
}

```
