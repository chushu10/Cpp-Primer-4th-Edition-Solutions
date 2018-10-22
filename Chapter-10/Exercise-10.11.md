# Exercise 10.11

What type can be used to subscript a `map`? What type does the sub-script operator return? Give a concrete example that is, define a `map` and then write the types that could be used to subscript the map and the type that would be returned from the subscript operator.

**Answer**:

```cpp
#include <iostream>
#include <map>
#include <string>
using namespace std;

int main(int argc, char const *argv[])
{
    map<string, int> map1;
    map<string, int>::key_type key1 = "hello";
    map<string, int>::mapped_type value1 = 1;
    map1[key1] = value1;
    return 0;
}
```