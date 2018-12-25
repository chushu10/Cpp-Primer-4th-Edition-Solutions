# Exercise 14.23

The class `CheckedPtr` represents a pointer that points to an array of `int`s. Define an overloaded subscript and dereference for this class. Have the operator ensure that the `CheckedPtr` is valid: It should not be possible to dereference or index one past the end of the array.

**Answer**:

```cpp
// ex1423.cc
#include <iostream>

class CheckedPtr
{
private:
    int *beg;
    int *curr;
    int *end;
public:
    CheckedPtr(int *b, int *e): beg(b), end(e), curr(b) { }
    CheckedPtr& operator++();
    CheckedPtr& operator--();
    CheckedPtr operator++(int);
    CheckedPtr operator--(int);
    int get_value() { return *curr; };
};

CheckedPtr& CheckedPtr::operator++()
{
    if (curr == end) {
        throw std::out_of_range
            ("increment past the end of CheckedPtr");
    }
    ++curr;
    return *this;
}

CheckedPtr& CheckedPtr::operator--()
{
    if (curr == beg) {
        throw std::out_of_range
            ("decrement past the begin of CheckedPtr");
    }
    --curr;
    return *this;
}

CheckedPtr CheckedPtr::operator++(int)
{
    CheckedPtr ret(*this);
    ++*this;
    return ret;
}

CheckedPtr CheckedPtr::operator--(int)
{
    CheckedPtr ret(*this);
    --*this;
    return ret;
}

int main()
{
    int arr[5] = {1,2,3,4,5};
    CheckedPtr cp(arr, arr+5);
    std::cout << cp.get_value() << std::endl;
    std::cout << (++cp).get_value() << std::endl;
    std::cout << (cp++).get_value() << std::endl;
    std::cout << (--cp).get_value() << std::endl;
    std::cout << (cp--).get_value() << std::endl;
    return 0;
}
```