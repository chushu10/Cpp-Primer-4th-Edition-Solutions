# Best Practices

- In C++, dynamic binding happens when a virtual function is called through a reference (or a pointer) to a base class. The fact that a reference (or pointer) might refer to either a base- or a derived- class object is the key to dynamic binding. Calls to virtual functions made through a reference (or pointer) are resolved at run time: The function that is called is the one defined by the actual type of the object to which the reference (or pointer) refers.
- In other words, the interface to the derived type is the combination of both the `protected` and `public` members.
- When we want to inherit the interface of a base class, then the derivation should be `public`.
- Regardless of which actual type the object has, the compiler treats the object as if it is a base type object. Treating a derived object as if it were a base type is safe, because every derived object has a base sub-object. Also, the derived class inherits the operations of the base class, meaning that any operation that might be performed on a base object is available through the derived object as well.
- On the other hand, an object is not polymorphic its type is known and unchanging. The dynamic type of an object (as opposed to a reference or pointer) is always the same as the static type of the object. Virtuals are resolved at run time *only* if the call is made through a reference or pointer.

|           | Virtual | Non-virtual |
| :-------: |:-------:|:-----------:|
| object    | compile-time<br>(base type) | compile-time<br>(base type) |
| reference | run-time<br>(actual type) | compile-time<br>(base type) |
| pointer   | run-time<br>(actual type) | compile-time<br>(base type) |

- Using different default arguments in the base and derived versions of the same virtual is almost guaranteed to cause trouble.
- Even though every `C` object contains an `A` part, the constructors for `C` may not initialize the `A` part directly. Instead, class `C` initializes `B`, and the constructor for class `B` in turn initializes `A`.
- Derived classes should **respect** the initialization intent of their base classes by using constructors rather than assigning to these members in the body of the constructor..