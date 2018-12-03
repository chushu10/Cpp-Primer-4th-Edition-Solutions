# Exercise 13.15

How many destructor calls occur in the following code fragment?

```cpp
void fcn(const Sales_item *trans, Sales_item accum)
{
    Sales_item item1(*trans), item2(accum);
    if (!item1.same_isbn(item2)) return;
    if (item1.avg_price() <= 99) return;
    else if (item2.avg_price() <= 99) return; // ...
}
```

**Answer**:

```cpp
void fcn(const Sales_item *trans, Sales_item accum)
{
    Sales_item item1(*trans), item2(accum);
    if (!item1.same_isbn(item2)) return; // destruct item1, item2, accum
    if (item1.avg_price() <= 99) return; // destruct item1, item2, accum
    else if (item2.avg_price() <= 99) return; // destruct item1, item2, accum
}
```