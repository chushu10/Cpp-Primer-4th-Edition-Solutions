# Exercise 13.4

Given the following sketch of a class, write a copy constructor that copies all the elements. Copy the object to which `pstring` points, not the pointer.

```cpp
struct NoName {
    NoName(): pstring(new std::string), i(0), d(0) { }
private:
    std::string *pstring;
    int    i;
    double d;
};
```

**Answer**:

```cpp
struct NoName {
    NoName(std::string str): pstring(new std::string(str)), i(0), d(0) { }
    NoName(const NoName &noname): pstring(new std::string(*(noname.pstring))), i(noname.i), d(noname.d) { }
private:
    std::string *pstring;
    int    i;
    double d;
};
```