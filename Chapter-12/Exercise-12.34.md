# Exercise 12.34

Define a nonmember function that adds two `Sales_item` objects.

**Answer**:

```cpp
friend Sales_item& add_items(Sales_item &item1, Sales_item &item2)
{
    if (item1.same_isbn(item2)) {
        item1.revenue_ += item2.revenue_;
        item1.units_sold_ += item2.units_sold_;
    }
    return item1;
}
```