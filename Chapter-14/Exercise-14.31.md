# Exercise 14.31

Define a function object to perform an if-then-else operation: The function object should take three parameters. It should test its first parameter and if that test succeeds, it should return its second parameter, otherwise, it should return its third parameter.

**Answer**:

```cpp
// ex1431.cc
#include <iostream>

struct IfThenElse {
    int operator() (bool first, int second, int third)
    {
        return first ? second : third;
    }
};

int main(int argc, char const *argv[])
{
    IfThenElse test;
    std::cout << test((3 + 1 == 4), 10, 20) << std::endl;
    return 0;
}
```