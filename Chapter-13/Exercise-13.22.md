# Exercise 13.22

What is a use count?

**Answer**:

The pointer like class associates a counter with the object to which the class points. The use count keeps track of how many objects of the class share the same pointer. When the use count goes to zero, then the object is deleted.