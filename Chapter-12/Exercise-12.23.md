# Exercise 12.23

Assume we have a class named `NoDefault` that has a constructor that takes an `int` but no default constructor.
Define a class `C` that has a member of type `NoDefault`. Define the default constructor for `C`.

**Answer**:

```cpp
class NoDefault {
public:
    NoDefault(int ival): ival_(ival) {}
private:
    int ival_;
};

class C {
public:
    C(NoDefault &nodefault): nodefault_(0) {}
private:
    NoDefault nodefault_;
};
```