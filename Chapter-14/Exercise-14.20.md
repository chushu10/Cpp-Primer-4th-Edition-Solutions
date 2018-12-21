# Exercise 14.20

In our sketch for the `ScreenPtr` class, we declared but did not define the assignment operator. Implement the `ScreenPtr` assignment operator.

**Answer**:

```cpp
ScreenPtr& ScreenPtr::operator=(const ScreenPtr &rhs)
{
    ++rhs.ptr->use;
    if (--ptr->use == 0)
        delete ptr;
    ptr = rhs.ptr;
    return *this;
}
```