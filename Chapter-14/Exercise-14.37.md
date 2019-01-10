# Exercise 14.37

Using the library function objects and adaptors, define an object to:

1. Find all values that are greater than 1024.
2. Find all strings that are not equal to `pooh`.
3. Multiply all values by 2.

```cpp
// ex1437.cc
#include <string>
#include <vector>
#include <iostream>
#include <functional>
#include <algorithm>
using namespace std;

int main(int argc, char const *argv[])
{
    vector<int> ivec;
    ivec.push_back(1000);
    ivec.push_back(1025);
    ivec.push_back(1026);
    ivec.push_back(1024);
    ivec.push_back(1031);
    vector<string> svec;
    svec.push_back("liu");
    svec.push_back("chu");
    svec.push_back("shu");
    svec.push_back("pooh");
    // 1. Find all values that are greater than 1024.
    cout << count_if(ivec.begin(), ivec.end(), bind2nd(greater<int>(), 1024)) << endl;
    // 2. Find all strings that are not equal to `pooh`.
    cout << count_if(svec.begin(), svec.end(), bind2nd(equal_to<string>(), "pooh")) << endl;
    // 3. Multiply all values by 2.
    transform(ivec.begin(), ivec.end(), ivec.begin(), bind2nd(multiplies<int>(), 2));
    vector<int>::const_iterator it = ivec.begin();
    for (; it != ivec.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl;
    return 0;
}
```