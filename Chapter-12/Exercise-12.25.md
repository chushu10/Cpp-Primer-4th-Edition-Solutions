# Exercise 12.25

Logically, we might want to supply `cin` as a default argument to the constructor that takes an `istream&`. Write the constructor declaration that uses `cin` as a default argument.

**Answer**:

```cpp
Sales_item(std::istream &is = std::cin);
```