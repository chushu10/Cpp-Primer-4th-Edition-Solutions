# Exercise 12.41

Given the classes `Foo` and `Bar` that you wrote for the exercises to Section 12.6.1 (p. 470 ), initialize the static members of `Bar`(It was `Foo` in the original content of *C++ Primer 4th edition*, but `Foo` has no static members). Initialize the int member to 20 and the `Foo` member to 0.

**Answer**:

```cpp
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

int Bar::xval_ = 20;
Foo Bar::foo_ = Foo(0);
```