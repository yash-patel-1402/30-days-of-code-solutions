## DAY 2

### **Problem statement 1**

---

**Summary :** Given a number `num`, check if all the digits are unique. If unique then output `The number is lucky.` else output `The number is unlucky.`.

**Solution 1:**

This is a typical use-case of a **set** data-structure. One by one insert the digit into the set and the moment you find element that is already in the set, conclude your output.

**Time Complexity :**

Since we are using set, set requires `log(n)` for insertion and since there can be total `n` insertion, total time complexity `O(n log n)` where `n` is the number of digits in the `num`

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <set>
#include <algorithm>
using namespace std;


int main() {
  string num;
  set<int> s;
  
  cin >> num;
  for (auto digit: num) {
    if (s.find(digit) != s.end()) {
      // digit is already in the set
      cout << "The number is unlucky." << endl;
      return 0;
    }
    s.insert(digit);
  }
  
  cout << "The number is lucky." << endl;
  return 0;
}
```

**Solution 2:**
Since this problem is using only digits (0-9), you can also use counting array that stores counts of the character. This way you will eliminate the time required by the set to insert and maintain itself.
Although this may not increase the efficiency for this current constraints of the problem, it would be helpful when the number of digits in `num` are large.

**Time Complexity :**

Since we are using count array, we can access any count in `O(1)` time, so total complexity would be `O(n)` since we are doing atmost `n` iterations over the number.

**CPP Solution :**

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <set>
#include <algorithm>
using namespace std;


int main() {
  string num;
  int counts[10] = {0};
  
  cin >> num;
  for (auto digit: num) {
    counts[digit - '0']++;
    if (counts[digit - '0'] > 1) {
      // there are more than 1 occurences of the same digit
      cout << "The number is unlucky." << endl;
      return 0;
    }
  }
  
  cout << "The number is lucky." << endl;
  return 0;
}
```

### **Problem statement 2**

---

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

### **Problem statement 3**

---

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
