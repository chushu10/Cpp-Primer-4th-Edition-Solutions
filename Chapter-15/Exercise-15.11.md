# Exercise 15.11

Choose one of the following general abstractions containing a family of types (or choose one of your own). Organize the types into an inheritance hierarchy:

(a) Graphical file formats (such as gif, tiff, jpeg, bmp)
(b) Geometric primitives (such as box, circle, sphere, cone)
(c) C++ language types (such as class, function, member function)

**Answer**:

```cpp
class file {
public:
    virtual size_t std::size() const { return n; }
private:
    size_t n;
    std::string path;
}

class gif : public file {
public:
    std::size_t size() const { ... }
}
```