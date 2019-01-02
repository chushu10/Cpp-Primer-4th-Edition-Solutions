# Exercise 14.28

We did not define a `const` version of the increment and decrement operators. Why?

**Answer**:

A `const` member may not change the data members of the object on which it operates. If we write code as below, the compiler will complain:

```cpp
CheckedPtr& CheckedPtr::operator++() const
{
    if (curr == end) {
        throw out_of_range("increment past the end of CheckedPtr");
    }
    ++curr; // cannot assign to non-static data member within const member function 'operator++'
    return *this;
}
```