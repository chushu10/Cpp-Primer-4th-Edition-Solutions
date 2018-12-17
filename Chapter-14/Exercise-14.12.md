# Exercise 14.12

Write the `Sales_item` operators so that `+` does the actual addition and `+=` calls `+`. Discuss the disadvantages of this approach compared to the way the operators were implemented in this section.

**Answer**:

```cpp
Sales_item& operator+=(const Sales_item &item)
{
    Sales_item ret = *this + item;
    *this = ret;
    return *this;
}
```

In this code, the temporary `ret` is needless. We first save the result of `+` in `ret`, and then copy `ret` to `*this`, which is a wast of time. 