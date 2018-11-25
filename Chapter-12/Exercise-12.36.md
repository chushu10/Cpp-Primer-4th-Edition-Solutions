# Exercise 12.36

What is a `static` class member? What are the advantages of `static` members? How do they differ from ordinary members?

**Answer**:

A class member that exists independently of any object of its class.

There are three advantages to using `static` members rather than globals:

1. The name of a `static` member is in the scope of the class, thereby avoiding name collisions with members of other classes or global objects.
2. Encapsulation can be enforced. A `static` member can be a private member; a global object cannot.
3. It is easy to see by reading the program that a `static` member is associated with a particular class. This visibility clarifies the programmer's intentions.

Ordinary non`static` data members exist in each object of the class type.