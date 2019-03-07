# Exercise 15.24

Why is it that, given

```cpp
Bulk_item bulk;
Item_base item(bulk);
Item_base *p = &bulk;
```

the expression

```cpp
p->net_price(10);
```

invokes the `Bulk_item` instance of `net_price`, whereas `item.net_price(10);` invokes the `Item_base` instance?

**Answer**:

Because `Item_base *p` is a pointer to the base class, and the `net_price` member is virtual. So that the compiler will generate code to determine which version to run based on the dynamic type of the object, which is `Base_item`.

However, `Item_base item` is an object, not a reference or pointer. So that there will be no dynamic binding behavior from compiler.