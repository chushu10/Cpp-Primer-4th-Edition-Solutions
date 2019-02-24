# Exercise 15.19

What if anything is likely to be incorrect about this class definition?

```cpp
class AbstractObject {
public:
    virtual void doit();
    // other members not including any of the copy-control functions
};
```

**Answer**:

This class is not a derived class. It is likely to be the base class of the class hierarchy.

However, without defining a virtual destructor, if we are about to delete a pointer to base class, then the base-class destructor is run and the members of the base are cleaned up. Since the static type of the pointer might differ from the dynamic type of the object that is being deleted. If the object really is a derived type, then the behavior is undefined.

We should define `AbstractObject` like this (even the virtual destructor does nothing):

```cpp
class AbstractObject {
public:
    virtual void doit();
    virtual ~AbstractObject() {}
    // other members
};
```