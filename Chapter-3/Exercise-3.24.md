# Exercise 3.24

Consider the sequence 1,2,3,5,8,13,21. Initialize a `bitset<32>` object that has one bit in each position corresponding to a number in this sequence. Alternatively, given an empty `bitset`, write a small program to turn on each of the appropriate bits.

**Answer**:

```cpp
#include <iostream>
#include <string>
#include <bitset>
#include <vector>
using std::cin;
using std::cout;
using std::endl;
using std::bitset;
using std::vector;
int main()
{
    // 1,2,3,5,8,13,21 is fibonacci sequence
    int a = 1, b = 2;
    int temp;
    bitset<32> bitvec;
    while (a < 32) {
        bitvec.set(a);
        temp = b;
        b = a + b;
        a = temp;
    }
    cout << "bitvec = " << bitvec << endl;
    return 0;
}
```