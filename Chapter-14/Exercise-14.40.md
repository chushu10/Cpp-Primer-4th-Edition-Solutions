# Exercise 14.40

Write operators that could convert a `Sales_item` to `string` and to `double` . What values do you think these operators should return? Do you think these conversions are a good idea? Explain why or why not.

**Answer**:

```cpp
// ex1440.cc
#include <iostream>
#include <string>
using namespace std;

class Sales_item {
public:
    operator std::string() const { return isbn; }
    operator double() const { return revenue; }
    Sales_item(std::string s, double d): isbn(s), revenue(d) {}
private:
    double revenue;
    std::string isbn;
};

int main(int argc, char const *argv[])
{
    Sales_item si("hello", 13.0);
    cout << si << endl;
    cout << string(si) << endl;
    return 0;
}
```