# Exercise 12.27

Which, if any, of the following statements are untrue? Why?

a. A class must provide at least one constructor.
b. A default constructor is a constructor with no parameters
for its parameter list.
c. If there are no meaningful default values for a class, the class should not provide a default constructor.
d. If a class does not define a default constructor, the compiler generates one automatically, initializing each data member to the default value of its associated type.

**Answer**:

a. No, you could write a class without constructors, the compiler will generate a default constructor for you. However, if there are members in your class that are of built-in type or compound type, they are uninitialized when your object are defined out side of global scope. More severely, if your class has members of class type, and that class type has no default constructor, your class must define one constructor explicitly, and that constructor must explicitly initialize its no-default class member.
b. Not so accurate. A default constructor is a constructor that either has no parameters, **or if it has parameters, all the parameters have default values**.
c. No, the default values should be "empty".
d. Right.