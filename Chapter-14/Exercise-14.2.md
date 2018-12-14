# Exercise 14.2

Write declarations for the overloaded input, output, addition and compound-assignment operators for `Sales_item`.

**Answer**:

```cpp
friend std::istream& operator>> (std::istream&, Sales_item&); // input
friend std::ostream& operator<< (std::ostream&, const Sales_item&); // output
Sales_item operator+(const Sales_item&, const Sales_item&); // addition
Sales_item& operator+=(const Sales_item&); // compound-assignment
```