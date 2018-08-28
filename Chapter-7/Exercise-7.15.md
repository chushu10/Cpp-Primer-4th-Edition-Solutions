# Exercise 7.15

Write a `main` function that takes two values as arguments and print their sum.

**Answer**:

```cpp
#include <iostream>
using std::cout;
using std::endl;

int main(int argc, char *argv[]) {
    if (argc != 3) {
        cout << "Please input two arguments";
        return -1;
    }
    cout << atof(argv[1]) + atof(argv[2]) << endl;
}
```