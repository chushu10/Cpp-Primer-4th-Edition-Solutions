# Exercise 12.16

What would happen if we defined `get_cursor` as follows:

```cpp
index Screen::get_cursor() const
{
    return cursor;
}
```

**Answer**:

The return type `index` is unknown, because it it not in the scope of class `Screen`.