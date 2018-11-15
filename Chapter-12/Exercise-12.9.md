# Exercise 12.9

Write your own version of the `Screen` class presented in this section, giving it a constructor to create a `Screen` from values for height, width, and the contents of the screen.

**Answer**:

```cpp
class Screen {
public:
    typedef std::string::size_type index;
    Screen (index height, index width, std::string contents)
    {
        this.height = height;
        this.width = width;
        this.contents = contents;
    }
private:
    std::string contents;
    index cursor;
    index height, width;
}
```