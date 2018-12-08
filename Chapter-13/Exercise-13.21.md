# Exercise 13.21

What would happen if we gave our `HasPtr` class a destructor that `delete`d its pointer member?

**Answer**:

If we have another `HasPtr` object copied from a `HasPtr` object, if we destruct any one of them, the other one's pointer member will point to a freed area, which will cause segment fault.