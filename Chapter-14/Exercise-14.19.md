# Exercise 14.19

Suggest alternative ways to define this operation.

**Answer**:

Define public member functions like this:

```cpp
std::string& CheckoutRecord::getNameByIndex(const std::size_t index)
{
    return wait_list[index]->first;
}

const std::string& CheckoutRecord::getNameByIndex(const std::size_t index) const
{
    return wait_list[index]->first;
}
```

These member functions are self explained and may not incur misunderstanding.