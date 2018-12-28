# Exercise 14.25

To behave like a pointer to an array, our `CheckedPtr` class should implement the equality and relational operators to determine whether two `CheckedPtr` s are equal, or whether one is less-than another, and so on. Add these operations to the `CheckedPtr` class.

**Answer**:

```cpp
// ex1425.cc
#include <iostream>

class CheckedPtr
{
    friend inline bool
        operator==(const CheckedPtr&, const CheckedPtr&);
    friend inline bool
        operator<(const CheckedPtr&, const CheckedPtr&);
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
    int& operator*() { return *curr; };
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

inline bool
operator==(const CheckedPtr &lhs, const CheckedPtr &rhs)
{
    return lhs.curr == rhs.curr;
}

inline bool
operator!=(const CheckedPtr &lhs, const CheckedPtr &rhs)
{
    return !(lhs == rhs);
}

inline bool
operator<(const CheckedPtr &lhs, const CheckedPtr &rhs)
{
    return lhs.curr < rhs.curr;
}

inline bool
operator>(const CheckedPtr &lhs, const CheckedPtr &rhs)
{
    return (!(lhs == rhs) && !(lhs < rhs));
}

int main()
{
    int arr[5] = {1,2,3,4,5};
    CheckedPtr cp(arr, arr+5);
    CheckedPtr cp2(arr, arr+5);
    std::cout << (cp == cp2) << std::endl;
    std::cout << (cp < cp2) << std::endl;
    std::cout << (cp > cp2) << std::endl;
    std::cout << "=====" << std::endl;
    ++cp2;
    std::cout << (cp == cp2) << std::endl;
    std::cout << (cp < cp2) << std::endl;
    std::cout << (cp > cp2) << std::endl;
    std::cout << "=====" << std::endl;
    ++cp;
    ++cp;
    std::cout << (cp == cp2) << std::endl;
    std::cout << (cp < cp2) << std::endl;
    std::cout << (cp > cp2) << std::endl;
    return 0;
}
```