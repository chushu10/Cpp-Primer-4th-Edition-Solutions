# Exercise 3.19

Test your program by printing the `vector`.

**Answer**:

```cpp
#include <iostream>
#include <string>
#include <vector>
using std::cin;
using std::cout;
using std::endl;
using std::vector;
int main()
{
    vector<int> nums(10, 1);

    // Exercise 3.19
    for (vector<int>::const_iterator iter = nums.begin(); iter != nums.end(); ++iter) {
        cout << *iter;
    }
    cout << endl;

    for (vector<int>::iterator iter = nums.begin(); iter != nums.end(); ++iter) {
        *iter = 2 * (*iter);
    }

    // Exercise 3.19
    for (vector<int>::const_iterator iter = nums.begin(); iter != nums.end(); ++iter) {
        cout << *iter;
    }
    cout << endl;

    return 0;
}
```