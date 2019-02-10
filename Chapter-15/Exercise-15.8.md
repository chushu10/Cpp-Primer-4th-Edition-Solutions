# Exercise 15.8

Given the following classes, explain each print function:

```cpp
struct base {
    string name() { return basename; }
    virtual void print(ostream &os) { os << basename; }
private:
    string basename;
};

struct derived {
    void print()
    {
        print(ostream &os);
        os << " " << mem;
    }
private:
    int mem;
};
```

If there is a problem in this code, how would you fix it?

**Answer**:

Of course, but there is not only one problem:

- First, the structure `derived` does not specify its base class.
- Second, the member `print` of structure `derived` is supposed to override the `print` member of structure `base`. However, they have different parameter list.
- Third, we should explicitly using the scope operator when we want to call the member defined in the base class.

How to fix:

```cpp
struct base {
    string name() { return basename; }
    virtual void print(ostream &os) { os << basename; }
private:
    string basename;
};

struct derived : public base {
    void print(ostream &os)
    {
        base::print(os);
        os << " " << mem;
    }
private:
    int mem;
};
```