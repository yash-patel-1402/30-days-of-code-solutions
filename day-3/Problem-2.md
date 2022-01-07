## DAY 3

### **Problem statement 2**

---

[**Problem link**](https://www.hackerrank.com/contests/day-3-of-30/challenges/fact-sum)

**Summary :** Basically this problem is about `factorian` numbers. It is the sum of factorials of all digits.

**Solution 1:** Digit by digit compute the factorial and add it to the `sum`

**Impovement over solution 1:** Since there are only 10 digits possible, you can precalculate them, so you don't have to repeat the calculation of the same digit.

**Time Complexity :** <img src="https://latex.codecogs.com/svg.image?O(log(n))" title="O(log(n))" /> where `n` is the `number`

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() {
    int factorails[10];
    factorails[0] = 1;
    factorails[1] = 1;

    for (int i = 2; i <= 9; i++) factorails[i] = i * factorails[i-1];

    string num;
    cin >> num;
    int sum = 0;
    for (auto digit: num) {
        sum += factorails[digit - '0'];
    }

    if (num == to_string(sum)) cout << "Yes" << endl;
    else cout << "No" << endl;
    return 0;
}

```
