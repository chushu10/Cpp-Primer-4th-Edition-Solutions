# Exercise 13.7

When does a class need to define an assignment operator?

**Answer**:

When it needs a copy constructor. But when does a class need to define a copy constructor? When we have to take control of what happens when objects are copied. Such classes often have a data member that is a pointer or that represents another resource that is allocated in the constructor. Other classes have bookkeeping that must be done whenever a new object is created. In both these cases, the copy constructor must be defined.