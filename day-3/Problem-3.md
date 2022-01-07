## DAY 3

### **Problem statement 3**

---

[**Problem link**](https://www.hackerrank.com/contests/day-3-of-30/challenges/count-special-number)

**Summary :** The task is to count the number of elements that occurs exactly <img src="https://latex.codecogs.com/svg.image?\left&space;\lfloor&space;\frac{N}{K}\right&space;\rfloor" title="\left \lfloor \frac{N}{K}\right \rfloor" /> times in the array.

Let's break the statement down.

Let `specialNumber` = number that occurs in array exactly <img src="https://latex.codecogs.com/svg.image?\left&space;\lfloor&space;\frac{N}{K}\right&space;\rfloor" title="\left \lfloor \frac{N}{K}\right \rfloor" /> times, where N is the size of the array and K is given input

Now count how many `specialNumber` are there in the array.

**Solution 1:** For every element of array, you can loop through the whole array and count how many times it occurs. Then decide if the current element is special or not and according to this update the `answer` counter.
And skip the elements that are already counted in the array.

**Time Complexity 1:** <img src="https://latex.codecogs.com/svg.image?O(n^{2})" title="O(n^{2})" /> since there are nested loop.

**CPP Solution 1:**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
#include <set>
using namespace std;


int main() {
  int n, k;
  cin >> n >> k;
  int arr[n];
  int requiredCountsForSpecialNum = n / k;

  for (int i = 0; i < n; i++) cin >> arr[i];

  int answer = 0;
  for (int i = 0; i < n; i++) {
    int currentElement = arr[i], currentElementCount = 0;
    if (currentElement == -1) continue;

    for (int j = 0; j < n; j++) {
      if (arr[j] == currentElement) {
        currentElementCount++;
        arr[j] = -1; // since this element is counted, update it with -1, so it will never be counted again
      }
    }
    if (currentElementCount == requiredCountsForSpecialNum) answer++;
  }

  cout << answer << endl;
  return 0;
}
```

**Solution 2 (Improved):** You can use hash-map data structure and store the counts of each number in the map. Then a single loop through the map for finding `specialNumber` will be sufficient.

**Time Complexity 2:** <img src="https://latex.codecogs.com/svg.image?O(n*log(n))" title="O(n*log(n))" /> Since insertion into map will take <img src="https://latex.codecogs.com/svg.image?O(log(n))" title="O(log(n))" /> times and there are atmost `n` insertions, total time complexity would be <img src="https://latex.codecogs.com/svg.image?O(n*log(n))" title="O(n*log(n))" />

**CPP Solution 2:**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
#include <map>
using namespace std;


int main() {
  int n, k;
  cin >> n >> k;
  int requiredCountsForSpecialNum = n / k;

  map<int, int> mp;
  for (int i = 0; i < n; i++) {
    int x;
    cin >> x;
    mp[x]++;
  }

  int answer = 0;
  for (auto i: mp) {
    int counts = i.second;
    if (counts == requiredCountsForSpecialNum) answer++;
  }

  cout << answer << endl;
  return 0;
}

```

```

```
