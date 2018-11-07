# Exercise 11.20

Now print the elements in reverse order using ordinary iterators.

**Answer**:

```cpp
#include <vector>
#include <iostream>
#include <iterator>
using namespace std;

int main()
{
    vector<int> ivec;
    ivec.push_back(1);
    ivec.push_back(2);
    ivec.push_back(3);
    ivec.push_back(4);
    ivec.push_back(5);
    ivec.push_back(6);

    vector<int>::iterator it = ivec.end() - 1;
    while (it != ivec.begin() - 1) {
        cout << *it-- << " ";
    }
    cout << endl;
    
    return 0;
}
```