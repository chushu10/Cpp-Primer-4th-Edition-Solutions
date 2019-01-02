# Exercise 14.30

Define a version of `CheckedPtr` that holds an array of `Screen`s. Implement the overloaded increment, decrement, dereference, and arrow operators for this class.

**Answer**:

```cpp
// ex1430.cc
#include <iostream>
#include <string>

class Screen {
    friend std::ostream& operator<<(std::ostream&, const Screen&);
public:
    Screen(const std::string &str): contents(str), cursor(0), height(0), width(0) { }
private:
    std::string contents;
    std::string::size_type cursor;
    std::string::size_type height, width;
};

std::ostream&
operator <<(std::ostream& os, const Screen &object) {
    os << object.contents;
    return os;
}

class CheckedPtr
{
private:
    Screen *beg;
    Screen *curr;
    Screen *end;
public:
    CheckedPtr(Screen *b, Screen *e): beg(b), end(e), curr(b) { }
    const Screen *operator->() const { return curr; }
    CheckedPtr& operator++();
    CheckedPtr& operator--();
    CheckedPtr operator++(int);
    CheckedPtr operator--(int);
    Screen& operator*() { return *curr; };
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
    Screen arr[5] = {Screen("hello"), Screen("world"), Screen("liu"), Screen("chu"), Screen("shu")};
    CheckedPtr cp(arr, arr+5);
    std::cout << *cp << std::endl;
    std::cout << *(++cp) << std::endl;
    std::cout << *(cp++) << std::endl;
    std::cout << *(--cp) << std::endl;
    std::cout << *(cp--) << std::endl;
    std::cout << cp.operator->() << std::endl;
    return 0;
}
```