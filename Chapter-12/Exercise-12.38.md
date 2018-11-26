# Exercise 12.38

Define a class named `Foo` that has a single data member of type `int`. Give the class a constructor that takes an `int` value and initializes the data member from that value. Give it a function that returns the value of its data member.

**Answer**:

```cpp
class Foo {
public:
    Foo(int ival): ival_(ival) {}
    int get_int() { return ival_; }
private:
    int ival_;
};
```