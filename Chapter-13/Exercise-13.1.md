# Exercise 13.1

What is a copy constructor? When is it used?

**Answer**:

The **copy constructor** is a special constructor that has a single parameter that is a (usually `const`) reference to the class type. The copy constructor is used explicitly when we define a new object and initialize it from an object of the same type. It is used implicitly when we pass or return objects of that type to or from functions.