# Exercise 12.39

Given the class `Foo` defined in the previous exercise, define another class `Bar` with two `static` data elements: one of type `int` and another of type `Foo`.

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
    static int ival_;
    static Foo foo_;
};
```