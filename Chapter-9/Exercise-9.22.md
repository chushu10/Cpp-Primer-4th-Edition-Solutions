# Exercise 9.22

Given that `vec` holds 25 elements, what does `vec.resize(100)` do? What if we next wrote `vec.resize(10)`?

**Answer**:

1. Adds 75 elements to back of `vec`, each element is value initialized.
2. Erases 90 elements from the back of `vec`.