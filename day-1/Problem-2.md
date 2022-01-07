## DAY 1

### **Problem statement 2**

---

[**Problem link :**] (https://www.hackerrank.com/contests/day-1-of-30/challenges/sum-of-digit-3-1)

**Summary :** Find the nth integer whose sum of all the digit is equal to 11.

**Solution :** A brute force approach would work here. Since `n` is bounded only to as big as 50, we can use brute force.

**CPP Solution :**

```cpp
#include <iostream>
using namespace std;

int sumOfDigits(int x) {
  string s = to_string(x);
  int sum = 0;
  for (auto ch: s) {
    sum += (ch - '0');
  }
  return sum;
}

int main() {
  int n;
  cin >> n;

  int currentNumber = 1;
  while (true) {
    if (sumOfDigits(currentNumber) == 11) {
      n--;
      if (n == 0) break;
    }
    currentNumber++;
  }

  cout << currentNumber << endl;
}
```
