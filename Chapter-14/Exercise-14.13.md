# Exercise 14.13

Which other arithmetic operators, if any, do you think `Sales_item` ought to support? Define those that you think the class should include.

**Answer**:

```cpp
Sales_item& operator-=(const Sales_item &item)
{
    units_sold -= item.units_sold;
    revenue -= item.revenue;
    return *this;
}

Sales_item operator-(const Sales_item &item1, const Sales_item &item2)
{
    Sales_item ret = item1;
    ret -= item2;
    return ret;
}
```