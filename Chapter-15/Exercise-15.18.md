# Exercise 15.18

What operations must a virtual destructor perform?

**Answer**:

There is no operation that a virtual destructor must perform. On the other hand, the root class of an inheritance hierarchy should define a virtual destructor even if the destructor has no work to do.