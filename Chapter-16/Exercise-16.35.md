# Exercise 16.35

Write a generic version of the `CheckedPtr` class described in Section 14.7 (p. 526).

**Answer**:

```cpp

#include <iostream>
#include <string>

template <class Type> class CheckedPtr {
private:
    Type *beg;
    Type *curr;
    Type *end;
public:
    CheckedPtr(Type *b, Type *e): beg(b), curr(b), end(e) { }
    const Type *operator->() const { return curr; }
    CheckedPtr& operator++();
    CheckedPtr& operator--();
    CheckedPtr operator++(int);
    CheckedPtr operator--(int);
    Type& operator*() { return *curr; };
};

template <class Type> CheckedPtr<Type>& CheckedPtr<Type>::operator++()
{
    if (curr == end) {
        throw std::out_of_range
            ("increment past the end of CheckedPtr");
    }
    ++curr;
    return *this;
}

template <class Type> CheckedPtr<Type>& CheckedPtr<Type>::operator--()
{
    if (curr == beg) {
        throw std::out_of_range
            ("decrement past the begin of CheckedPtr");
    }
    --curr;
    return *this;
}

template <class Type> CheckedPtr<Type> CheckedPtr<Type>::operator++(int)
{
    CheckedPtr<Type> ret(*this);
    ++*this;
    return ret;
}

template <class Type> CheckedPtr<Type> CheckedPtr<Type>::operator--(int)
{
    CheckedPtr<Type> ret(*this);
    --*this;
    return ret;
}

int main()
{
    std::string arr[5] = {"hello", "world", "liu", "chu", "shu"};
    CheckedPtr<std::string> cp(arr, arr+5);
    std::cout << *cp << std::endl;
    std::cout << *(++cp) << std::endl;
    std::cout << *(cp++) << std::endl;
    std::cout << *(--cp) << std::endl;
    std::cout << *(cp--) << std::endl;
    std::cout << cp.operator->() << std::endl;
    return 0;
}

```
