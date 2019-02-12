# Exercise 15.12

For the class you chose in the previous exercise, identify some of the likely virtual functions as well as public and protected members.

**Answer**:

```cpp
class file {
public:
    virtual size_t std::size() const { return n; }
private:
    size_t n;
protected:
    std::string path;
}

class gif : public file {
public:
    std::size_t size() const { ... }
}
```