# Exercise 14.21

Define a class that holds a pointer to a `ScreenPtr`. Define the overloaded arrow operator for that class.

**Answer**:

```cpp
class ScreenPtrPtr {
public:
    ScreenPtr* operator->() { return ptr; }
private:
    ScreenPtr *ptr;
};
```