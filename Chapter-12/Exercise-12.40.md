# Exercise 12.40

Using the classes from the previous two exercises, add a pair of `static` member functions to class `Bar`. The first `static`, named `FooVal`, should return the value of class `Bar`'s `static` member of type `Foo`. The second member, named `callsFooVal`, should keep a count of how many times `xval` is called.

**Answer**:

```cpp
#include <iostream>

class Foo {
public:
    Foo(int ival): ival_(ival) {}
    int get_int() { return ival_; }
private:
    int ival_;
};

class Bar {
public:
    static Foo FooVal() { ++xval_; return foo_; }
    static int callsFooVall() { return xval_;}
    static int xval_;
    static Foo foo_;
};

int Bar::xval_ = 0;
Foo Bar::foo_ = Foo(10);

int main()
{
    std::cout << Bar::FooVal().get_int() << std::endl;
    std::cout << Bar::callsFooVall() << std::endl;
    std::cout << Bar::FooVal().get_int() << std::endl;
    std::cout << Bar::callsFooVall() << std::endl;
    std::cout << Bar::FooVal().get_int() << std::endl;
    std::cout << Bar::callsFooVall() << std::endl;
    std::cout << Bar::FooVal().get_int() << std::endl;
    std::cout << Bar::callsFooVall() << std::endl;
    std::cout << Bar::FooVal().get_int() << std::endl;
    std::cout << Bar::callsFooVall() << std::endl;
    std::cout << Bar::FooVal().get_int() << std::endl;
    std::cout << Bar::callsFooVall() << std::endl;
    std::cout << Bar::FooVal().get_int() << std::endl;
    std::cout << Bar::callsFooVall() << std::endl;
}
```