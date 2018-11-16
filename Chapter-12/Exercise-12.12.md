# Exercise 12.12

Explain the difference between a class declaration and definition. When would you use a class declaration? A class
definition?

**Answer**:

- Declaration: introduces the name of the class into the program and indicates that the name refers to a class type.
- Definition: a class is completely defined once the closing curly brace appears.

A class must be fully defined before objects of that type are created. The class must be defined and not just declared so that the compiler can know how much storage to reserve for an object of that class type. Similarly, the class must be defined before a reference or pointer is used to access a member of the type.

A common use of class forward declarations is to write classes that are mutually dependent on one another.