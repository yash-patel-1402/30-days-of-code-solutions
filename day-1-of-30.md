## DAY 1

### **Problem statement 1**

---

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

### **Problem statement 2**

---

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

### **Problem statement 3**

---

**Summary :** According to the following formula update the value of `n` repeatedly till `n` becomes 1 and count the number of times you had to update the value of `n`. 

<img src="https://latex.codecogs.com/svg.image?n&space;=&space;n&space;/&space;2\qquad&space;if\&space;n\&space;is\&space;even&space;\\&space;n&space;=&space;3&space;*&space;n&space;&plus;&space;1\qquad&space;if\&space;n\&space;is\&space;odd" title="n = n / 2\qquad if\ n\ is\ even \\ n = 3 * n + 1\qquad if\ n\ is\ odd" />

**Solution :** Just follow the formula and apply the update to the n.

**Facts on Collatz conjecture :** The problem asked in the question is called collatz conjecture. It’s still not proved in mathematics if the sequence can terminate for all integers. Since [this article](https://www.quantamagazine.org/why-mathematicians-still-cant-solve-the-collatz-conjecture-20200922/ "https://www.quantamagazine.org/why-mathematicians-still-cant-solve-the-collatz-conjecture-20200922/") suggests that  this sequence will terminate to 1 for all <img src="https://latex.codecogs.com/svg.image?n&space;<=&space;2^{68}" title="n <= 2^{68}" /> it’s okay for our solution to assume that while loop terminate at some point, but in mathematics it’s still unproved for infinitely larger numbers.

**CPP Solution :** 

```cpp
#include <iostream>
using namespace std;

int main() {
  int n;
  cin >> n;
  
  int count = 0;
  while (n != 1) {
    if (n % 2 == 0) n /= 2;
    else n = 3 * n + 1;
    count++;
  }
  count++;
  
  cout << count << endl;
}
```

  
