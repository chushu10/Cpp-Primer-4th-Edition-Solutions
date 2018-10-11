# Exercise 9.31

Can a container have a capacity less than its size? Is a capacity equal to its size desirable? Initially? After an element is inserted? Why or why not?

**Answer**:

- No, a container must not have a capacity less than its size, the capacity is always no less than the size.
- It's not desirable to have capacity and size equal, since each time we insert an element to a container whose elements are continuously stored, we have to allocate new space for this element, which is time consuming.