# Exercise 15.13

Given the following classes, list all the ways a member function in `C1` might access the `static` members of `ConcreteBase`. List all the ways an object of type `C2` might access those members.

```cpp
struct ConcreteBase {
    static std::size_t object_count();
protected:
    static std::size_t obj_count;
};
struct C1 : public ConcreteBase { /* . . . */ };
struct C2 : public ConcreteBase { /* . . . */ };
```

**Answer**:

1. Through base class `ConcreteBase`.
2. Through inheritance.
3. Through derived object `C2` or `C1`.
4. Through derived class itself.