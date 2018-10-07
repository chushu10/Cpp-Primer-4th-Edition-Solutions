# Exercise 9.23

What, if any, restrictions does using `resize` with a single size argument place on the element types?

**Answer**:

If the size argument is less than the original size of the container, the excess elements are discarded. If new elements must be added, they are value initialized.