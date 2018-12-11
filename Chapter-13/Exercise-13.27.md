# Exercise 13.27

The value like `HasPtr` class defines each of the copy-control members. Describe what would happen if the class defined

a. The copy constructor and destructor but no assignment operator.
b. The copy constructor and assignment operator but no destructor.
c. The destructor but neither the copy constructor nor assignment operator.

**Answer**:

a. When assigning a `HasPtr` object to another, we only get the `ptr` pointer itself copied, making the pointers of the two `HasPtr` point to the same object. If one of the `HasPtr` object is deleted, the other one's `ptr` member will be a dangling pointer.
b. When the `HasPtr` object is deleted, the object pointed by the `ptr` pointer still remains. However, there will be no pointer point to that memory any more, causing memory leakage.
c. `ptr` member will point to object allocated by others, deleting the pointer will be a disaster if the underlining object has already been deleted.