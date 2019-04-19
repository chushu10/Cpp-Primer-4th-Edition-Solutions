# Exercise 15.38

Why did we define two private sections in `Basket`?

**Answer**:

Well, the second part:

```cpp
std::multiset<Sales_item, Comp> items;
```

needs to know what `Comp` is.