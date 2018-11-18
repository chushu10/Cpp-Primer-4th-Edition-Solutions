# Exercise 12.17

What would happen if we put the `typedef` in the `Screen` class as the last line in the class?

**Answer**:

It will disobey the **first rule**: A name must be defined before it can be used. So that all the places using `index` will result in error.