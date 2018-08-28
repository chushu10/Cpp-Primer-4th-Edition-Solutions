# Exercise 7.16

Write a program that could accept the options presented in this section. Print the values of the arguments passed to `main`.

**Answer**:

```cpp
#include <iostream>
using std::cout;
using std::endl;

int main(int argc, char *argv[]) {
    for (int i = 0; i != argc; ++i) {
        cout << argv[i] << " ";
    }
    cout << endl;
}
```