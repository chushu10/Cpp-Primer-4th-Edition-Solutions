# Exercise 13.5

Which class definition is likely to need a copy constructor?

a. A `Point3w` class containing four `float` members
b. A `Matrix` class in which the actual matrix is allocated dynamically within the constructor and is deleted within its destructor
c. A `Payroll` class in which each object is provided with a unique ID
d. A `Word` class containing a `string` and a `vector` of line and column location pairs

**Answer**:

a. Don't need, all four members are built-in type.
b. Need a copy constructor, because there is resource that is allocated in the constructor.
c. Is this the bookkeeping case? If so, then we do need a copy constructor. **Please make a pull request if you have other opinions**.
d. Don't need, all members are class type(`vector` of pairs is still a class, which has its own copy constructor that can be used by class synthesized copy constructor).