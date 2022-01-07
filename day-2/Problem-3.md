## DAY 2

### **Problem statement 3**

---

[**Problem link**](https://www.hackerrank.com/contests/day-2-of-30/challenges/keep-arranging)

**Summary :** Find the nth harmonic number in the following harmonic series

<img src="https://latex.codecogs.com/svg.image?H1&space;=&space;1\\H2&space;=&space;H1&space;&plus;&space;1/2\\H3&space;=&space;H2&space;&plus;&space;1/3\\H4&space;=&space;H3&space;&plus;&space;1/4\\.&space;.&space;.\\Hn&space;=&space;Hn-1&space;&plus;&space;1/n" title="H1 = 1\\H2 = H1 + 1/2\\H3 = H2 + 1/3\\H4 = H3 + 1/4\\. . .\\Hn = Hn-1 + 1/n" />

**Solution :** It's pretty straight forward, just follow the formula.
**If you are using C/C++ or any language which type castes the number automatically then remember to add type casting since divide will automatically convert the argument into integer if both the argument of \ operator is integer**

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
#include <iomanip>
using namespace std;


int main() {
    int n;
    cin >> n;
    double h = 0;
    for (int c = 1; c <= n; c++) {
        h += ((double)1 / c);
    }
    cout << "Harmonic sum upto 4 decimal places: " << fixed << setprecision(4) << h << endl;
    return 0;
}
```
