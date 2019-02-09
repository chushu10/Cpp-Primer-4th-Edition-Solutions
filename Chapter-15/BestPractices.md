# Best Practices

- In C++, dynamic binding happens when a virtual function is called through a reference (or a pointer) to a base class. The fact that a reference (or pointer) might refer to either a base- or a derived- class object is the key to dynamic binding. Calls to virtual functions made through a reference (or pointer) are resolved at run time: The function that is called is the one defined by the actual type of the object to which the reference (or pointer) refers.
- In other words, the interface to the derived type is the combination of both the `protected` and `public` members.
- When we want to inherit the interface of a base class, then the derivation should be `public`.