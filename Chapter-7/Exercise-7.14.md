# Exercise 7.14

Write a program to sum the elements in a `vector<double>`.

**Answer**:

```cpp
#include <vector>
#include <iostream>
using std::vector;
using std::cout;
using std::endl;

double doubleSum(vector<double>::const_iterator beg,
                 vector<double>::const_iterator end)
{
    double sum = 0;
    while (beg != end) {
        sum += *beg++;
    }
    return sum;
}

int main(int argc, char const *argv[])
{
    vector<double> dvec;
    dvec.push_back(0.1);
    dvec.push_back(2.1);
    dvec.push_back(5.8);
    dvec.push_back(11.3);
    dvec.push_back(2.05);
    dvec.push_back(44.02);
    cout << doubleSum(dvec.begin(), dvec.end()) << endl;
    return 0;
}
```