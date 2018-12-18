# Exercise 14.16

Should `CheckoutRecord` define any other assignment operators? If so, explain which types should be used as operands and why. Implement the assignment operators for those types.

**Answer**:

```cpp
CheckoutRecord& CheckoutRecord::operator=(double rhs)
{
    *this = CheckoutRecord(rhs);
    return *this;
}
```