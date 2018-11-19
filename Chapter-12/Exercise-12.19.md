# Exercise 12.19

Provide one or more constructors that allows the user of this class to specify initial values for none or all of the data elements of this class:

```cpp
class NoName {
public:
// constructor(s) go here ...
private:
    std::string *pstring;
    int ival;
    double dval;
};
```

Explain how you decided how many constructors were needed and what parameters they should take.

**Answer**:

```cpp
class NoName {
public:
    NoName(); // initial values for none
    NoName(const std::string &, int, double); // initial values for all
private:
    std::string *pstring;
    int ival;
    double dval;
};

NoName::NoName(const std::string &str, int int_val, double d_val)
{
    pstring = new std::string(str);
    ival = int_val;
    dval = d_val;
}
```

One constructor without parameters for none initial value, and another constructor with all three parameters for all initial values. It's clear, and don't need further explanation.