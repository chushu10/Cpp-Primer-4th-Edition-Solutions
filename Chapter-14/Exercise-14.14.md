# Exercise 14.14

Define a version of the assignment operator that can assign an `isbn` to a `Sales_item`.

**Answer**:

```cpp
Sales_item& Sales_item::operator=(const std::string &rhs)
{
    isbn = rhs;
    return *this;
}
```