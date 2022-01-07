## DAY 1

### **Problem statement 1**

---

[**Problem link :**](https://www.hackerrank.com/contests/day-1-of-30/challenges/difference-between-sum-and-product-of-digit)

**Summary :** Take sum and product of all the digits and give absolute difference between them.

**Solution :**

Let’s take the sum of all the digit as `sumOfDigits` using a for loop.

Let’s take the product of all the digit as `productOfDigits` using a for loop.

Then print `|productOfDigits - sumOfDigits|`

**Time Complexity :**

Since there is only for loop which is going to execute for `n` times. So total time complexity is <img src="https://latex.codecogs.com/gif.latex?\theta(n)" />

**CPP Solution :**

```cpp
#include <iostream>
using namespace std;

int main() {
  int n;
  cin >> n;
  string s;
  cin >> s;

  int sumOfDigits = 0, productOfDigits = 1;
  for (int i = 0; i < s.size(); i++) {
    int digit = s[i] - '0';
    sumOfDigits += digit;
    productOfDigits *= digit;
  }

  cout << abs(productOfDigits - sumOfDigits) << endl;
}
```
