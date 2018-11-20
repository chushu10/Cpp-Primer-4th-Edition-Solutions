# Exercise 12.21

Write the default constructor using a constructor initializer for class that contains the following members: a `const` `string`, an `int`, a `double*`, and an `ifstream&`. Initialize the `string` to hold the name of the class.

**Answer**:

```cpp
class NoName {
public:
    NoName(const std::string &name, int ival, double *pd, std::ifstream &ifs):
    name_(name), ival_(ival), pd_(pd), ifs_(ifs) {}
private:
    const std::string name_;
    int ival_;
    double *pd_;
    std::ifstream &ifs_;
};
```