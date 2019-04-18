# Exercise 15.36

What is the underlying type of `Basket::const_iter`?

**Answer**:

According to the definition in class `Basket`:

```cpp
typedef std::multiset<Sales_item, Comp> set_type;
typedef set_type::const_iterator const_iter;
```

The underlying type of `Basket::const_iter` is `set_type::const_iterator`. The underlying type of `set_type` is `std::multiset<Sales_item, Comp>`. After all, the underlying type of `Basket::const_iter` is:

```cpp
std::multiset<Sales_item, Comp>::const_iterator
```