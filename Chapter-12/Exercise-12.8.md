# Exercise 12.8

Define `Sales_item::avg_price` as an `inline` function.

**Answer**:

```cpp
inline double Sales_item::avg_price() const
{
    if (units_sold)
        return revenue/units_sold;
    else
        return 0;
}
```