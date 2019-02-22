# Exercise 15.17

Describe the conditions under which a class should have a virtual destructor.

**Answer**:

The root class of an inheritance hierarchy should define a virtual destructor even if the destructor has no work to do.