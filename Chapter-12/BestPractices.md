# Best Practices

- If the class is defined with the `struct` keyword, then members defined before the first access label are `public`; if the class is defined using the class keyword, then the members are `private`.
- An incomplete type may be used to define only pointers or references to the type or to declare (but not define) functions that use the type as a paremeter or return type.
- The class must be defined before a reference or pointer is used to access a member of the type.
- A class is not defined until its class body is complete, a class cannot have data members of its own type. But can have data members that are pointers or references to its own type.