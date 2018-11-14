# Exercise 12.5

What are the access labels supported by C++ classes? What kinds of members should be defined after each access label? What, if any, are the constraints on where and how often an access label may appear inside a class definition?

**Answer**:

- `private`: member variables to be hidden from users of the class.
- `public`: member functions to be provided to users of the class.
- `protected`: we will talk about it later.

There are no restrictions on how often an access label may appear. Each access label specifies the access level of the succeeding member definitions. The specified access level remains in effect until the next access label is encountered or the closing right brace of the class body is seen.