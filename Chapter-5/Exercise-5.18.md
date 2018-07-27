# Exercise 5.18

Write a program that defines a `vector` of pointers to `string`s. Read the `vector`, printing each `string` and its corresponding size.

**Answer**:

```cpp
#include <iostream>
#include <string>
#include <vector>
using std::cout;
using std::cin;
using std::endl;
using std::string;
using std::vector;

int main(int argc, char const *argv[])
{
    vector<string *> strPtrVec;
    string hello = "hello";
    string world = "world";
    string chu = "chu";
    string shu = "shu";
    strPtrVec.push_back(&hello);
    strPtrVec.push_back(&world);
    strPtrVec.push_back(&chu);
    strPtrVec.push_back(&shu);
    for (vector<string *>::iterator iter = strPtrVec.begin();
                                    iter != strPtrVec.end();
                                    ++iter) {
        cout << **iter << "(" << (*iter)->size() << ")" << " ";
    }
    cout << endl;
    return 0;
}
```