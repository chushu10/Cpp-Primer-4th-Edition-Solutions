# Best Practices

- If the class is defined with the `struct` keyword, then members defined before the first access label are `public`; if the class is defined using the class keyword, then the members are `private`.
- An incomplete type may be used to define only pointers or references to the type or to declare (but not define) functions that use the type as a paremeter or return type.
- The class must be defined before a reference or pointer is used to access a member of the type.
- A class is not defined until its class body is complete, a class cannot have data members of its own type. But can have data members that are pointers or references to its own type.
- Ordinarily, it is a bad idea to define an object as part of a class definition. Doing so obscures what's happening. It is confusing to readers to combine definitions of two different entities the class and a variable in a single statement.
- If the function is defined outside the class body, then the name used for the return type is outside the class scope.
- A name must be defined before it can be used。
- A constructor is used to initialize an object regardless of whether the object is `const`.
- The constructor initializer is specified only on the constructor definition, not its declaration.
- Conceptually, we can think of a constructor as executing in two phases: (1) the initialization phase and (2) a general computation phase. The computation phase consists of all the statements within the body of the constructor.
- We must use an initializer for any `const` or reference member or for any member of a class type that does not have a default constructor.
- The constructor initializer list specifies only the values used to initialize the members, **not the order** in which those initializations are performed. So, it is a good idea to write constructor initializers in the same order as the members are declared. Moreover, when possible, avoid using members to initialize other members.
- The compiler generates a default constructor automatically only if a class defines *no* constructors.
- When objects are defined at local scope, then members of built-in or compound type are *uninitialized*.
- [A default constructor is a constructor that either has no parameters, or if it has parameters, all the parameters have default values](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.3.0/com.ibm.zos.v2r3.cbclx01/cplr376.htm).
- In practice, it is almost always right to provide a default constructor if other constructors are being defined. Ordinarily the initial values given to the members in the default constructor should indicate that the object is "empty."
- Ordinarily, single-parameter constructors should be `explicit` unless there is an obvious reason to want to define an implicit conversion. Making constructors `explicit` may avoid mistakes, and a user can explicitly construct an object when a conversion is useful.
- A friend declaration introduces the named class or nonmember function into the surrounding scope. Moreover, a friend function may be defined inside the class. The scope of the function is exported to the scope enclosing the class definition.