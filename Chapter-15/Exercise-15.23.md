# Exercise 15.23

Given the following base- and derived-class definitions

```cpp
struct Base {
    foo(int);
protected:
    int bar;
    double foo_bar;
};

struct Derived : public Base {
    foo(string);
    bool bar(Base *pb);
    void foobar();
protected:
    string bar;
};
```

identify the errors in each of the following examples and how each might be fixed:
(a) `Derived d; d.foo(1024);`
(b) `void Derived::foobar() { bar = 1024; }`
(c) `bool Derived::bar(Base *pb) { return foo_bar == pb->foo_bar; }`

**Answer**:

(a) `Derived::foo` hides the base class member `Base::foo`, so that there is no member function named `foo` that takes a `int` as parameter. Probable fix: `Derived d; d.foo("1024");`.
(b) `Derived::bar` hides the base class member `Base::bar`, so that there is no member named `bar` that is an `int` type. Probable fix: `void Derived::foobar() { bar = "1024"; }` or `void Derived::foobar() { Base::bar = 1024; }`.
(c) The `Derived::bar` function will always return `true`.