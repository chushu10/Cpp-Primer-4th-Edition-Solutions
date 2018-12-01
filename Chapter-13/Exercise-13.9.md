# Exercise 13.9

The first exercise in Section 13.1.2 (p. 481 ) included a skeletal definition for class `NoName`. Determine whether that class needs an assignment operator. If so, implement it.

**Answer**:

```cpp
struct NoName {
    NoName(): pstring(new std::string), i(0), d(0) { }
private:
    std::string *pstring; // NoName definitely needs an assignment operator because of this pointer member
    int    i;
    double d;
};

NoName& NoName::operator=(const NoName &noname)
{
    pstring = new std::string(*(noname.pstring)));
    i = noname.i;
    d = noname.d;
    return *this;
}
```