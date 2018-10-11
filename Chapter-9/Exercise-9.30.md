# Exercise 9.30

Write a program to explore the allocation strategy followed by the library you use for `vector` objects.

**Answer**:

```cpp
#include <vector>
#include <iostream>
using namespace std;

int main(int argc, char const *argv[])
{
    vector<int> ivec;
    cout << "ivec.size() = " << ivec.size() << endl;
    cout << "ivec.capacity() = " << ivec.capacity() << endl;
    ivec.push_back(1);
    cout << endl;
    cout << "pushed 1 into vector" << endl;
    cout << "ivec.size() = " << ivec.size() << endl;
    cout << "ivec.capacity() = " << ivec.capacity() << endl;
    ivec.push_back(2);
    ivec.push_back(3);
    ivec.push_back(4);
    cout << endl;
    cout << "pushed 2,3,4 into vector" << endl;
    cout << "ivec.size() = " << ivec.size() << endl;
    cout << "ivec.capacity() = " << ivec.capacity() << endl;
    for (int i = 5; i < 100; ++i) {
        ivec.push_back(i);
    }
    cout << endl;
    cout << "pushed 5 to 99 into vector" << endl;
    cout << "ivec.size() = " << ivec.size() << endl;
    cout << "ivec.capacity() = " << ivec.capacity() << endl;
    for (int i = 100; i < 130; ++i) {
        ivec.push_back(i);
    }
    cout << endl;
    cout << "pushed 100 to 129 into vector" << endl;
    cout << "ivec.size() = " << ivec.size() << endl;
    cout << "ivec.capacity() = " << ivec.capacity() << endl;
    return 0;
}
```

For me, the output is:

```bash
ivec.size() = 0
ivec.capacity() = 0

pushed 1 into vector
ivec.size() = 1
ivec.capacity() = 1

pushed 2,3,4 into vector
ivec.size() = 4
ivec.capacity() = 4

pushed 5 to 99 into vector
ivec.size() = 99
ivec.capacity() = 128

pushed 100 to 129 into vector
ivec.size() = 129
ivec.capacity() = 256
```

It can be seen that when `ivec`'s capacity was 128, if the 129th element was pushed into `ivec`, then its size was incremented to 256 (doubled).