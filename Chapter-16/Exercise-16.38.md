# Exercise 16.38

Write a `Screen` class template that uses nontype parameters to define the height and width of the `Screen`.

**Answer**:

```cpp
template <int hi, int wid>
class Screen {
public:
    // template nontype parameters used to initialize data members
    Screen(): screen(hi * wid, '#'), cursor (0), height(hi), width(wid) { }
    // ...
private:
    std::string screen;
    std::string::size_type cursor;
    std::string::size_type height, width;
};
```
