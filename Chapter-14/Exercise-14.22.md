# Exercise 14.22

A smart pointer probably should define the equality and inequality operators to test whether two pointers are equal or unequal. Add these operations to the `ScreenPtr` class.

**Answer**:

```cpp
inline bool operator==(const ScreenPtr &lhs, const ScreenPtr &rhs)
{
    return lhs.ptr == rhs.ptr;
}

inline bool operator!=(const ScreenPtr &lhs, const ScreenPtr &rhs)
{
    return !(lhs == rhs);
}
```