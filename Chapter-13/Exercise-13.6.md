# Exercise 13.6

The parameter of the copy constructor does not strictly need to be const, but it does need to be a reference. Explain the rationale for this restriction. For example, explain why the following definition could not work.

```cpp
Sales_item::Sales_item(const Sales_item rhs);
```

**Answer**:

Well, if the parameter is not a reference, then we should copy that object to our copy constructor which makes no sense since our copy constructor is copying it!

In the code above, when we still not fully defined our copy constructor, but we have to copy the argument which is quite a dilemma.