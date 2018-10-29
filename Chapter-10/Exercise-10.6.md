# Exercise 10.6

Could we define a `map` from `vector<int>::iterator` to `int` ? What about from `list<int>::iterator` to `int`? What about from `pair<int, string>` to `int`? In each case, if not, explain why not.

**Answer**:

- We can define a `map` from `vector<int>::iterator` or `pair<int, string>` to `int`, because both `vector<int>::iterator` and `pair<int, string>` support the `<` operator.
- We cannot define a `map` from `list<int>::iterator` to `int`, because `list<int>::iterator` type does not support `<` operator.

> The key type needs to support only the < operator. There is no requirement that it support the other relational or equality operators.

> The reason that only vector and deque support the relational operators is that only vector and deque offer fast, random access to their elements. So it is possible for their iterators to efficiently implement the arithmetic and relational operations.

Example:

```cpp
#include <vector>
#include <list>
#include <utility>
#include <map>
#include <string>
using namespace std;

int main(int argc, char const *argv[])
{
    map< vector<int>::iterator, int > map1;
    vector<int> int_vec;
    int_vec.push_back(1);
    int_vec.push_back(2);
    int_vec.push_back(3);
    vector<int>::iterator it1 = int_vec.begin();
    map1.insert(map< vector<int>::iterator, int >::value_type(it1, 5));

    map< list<int>::iterator, int > map2;
    list<int> int_list;
    int_list.push_back(1);
    int_list.push_back(2);
    int_list.push_back(3);
    list<int>::iterator it1 = int_list.begin();
    map2.insert(map< list<int>::iterator, int >::value_type(it1, 5)); // Compile error

    map< pair<int, string>, int > map3;
    pair<int, string> pair1(1, "one");
    pair<int, string> pair2(2, "two");
    pair<int, string> pair3(3, "three");
    map3.insert(map< pair<int, string>, int>::value_type(pair1, 11));
    return 0;
}
```