## DAY 2

### **Problem statement 2**

---

[**Problem link**](https://www.hackerrank.com/contests/day-2-of-30/challenges/frame-it-up)

**Summary :** Given a number `num` find the binary equivalent of the number and output it

**Solution :** Either you can use the library function given by language itself, or you can follow the procedure of converting decimal into binary. [Here is how to convert it](https://www.geeksforgeeks.org/program-decimal-binary-conversion/)

**Time Complexity :**

Since there are atmost `log(num) + 1` digits in `num`, and also we are going bit by bit, we have final time complexity of `O(log(num))`

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() {
    int num;
    cin >> num;
    string binaryString;

    while (num != 0) {
        // using bitwise 'num & 1' you can find if the least significant bit is 1 or 0
        if (num & 1) binaryString += '1';
        else binaryString += '0';

        // since least significant bit is added to answer, now right shift the current number
        // to one position right
        num >>= 1;
    }

    // since we are appending least significant --> to --> most significant bit
    // our string is in reverse order, so reverse it again so it will give correct
    // bit pattern
    reverse(binaryString.begin(), binaryString.end());
    cout << binaryString << endl;
    return 0;
}
```
