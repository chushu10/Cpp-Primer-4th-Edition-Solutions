# Exercise 13.12

Determine whether the `NoName` class sketched in the exercises on page 481, is likely to need a destructor. If so, implement it.

**Answer**:

```cpp
// The NoName class
struct NoName {
    NoName(): pstring(new std::string), i(0), d(0) { }
private:
    std::string *pstring;
    int    i;
    double d;
};
```

It needs a destructor, since the synthesized destructor does not delete the object pointed to by a pointer member.

```
struct NoName {
    NoName(): pstring(new std::string), i(0), d(0) { }
    ~NoName()
    {
        delete pstring;
    }
private:
    std::string *pstring;
    int    i;
    double d;
};
```