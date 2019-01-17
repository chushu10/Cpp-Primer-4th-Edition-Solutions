# Best Practices

- Generally, output operators should print the contents of the object, with minimal formatting. They should not print a newline.
- IO operators usually read or write the non`public` data members. As a consequence, classes often make the IO operators `friend`s.
- Ordinarily, the relational operators, like the equality operators, should be defined as nonmember functions.
- The overloaded arrow operator must return either a pointer to a class type or an object of a class type that defines its own operator arrow.
- Pointer arithmetic is legal only if the original pointer and the newly calculated pointer address elements of the same array or an element one past the end of that array. If we have a pointer to an object, we can also compute a pointer that points just after that object by adding one to the pointer.
- The function-call operator must be declared as a member function. A class may define multiple versions of the call operator, each of which differs as to the number or types of their parameters.
- A **binder** is a function adaptor that **converts a binary function object into a unary function object** by binding one of the operands to a given value.
- A **negator** is a function adaptor that reverses the truth value of a predicate function object.
- A **conversion operator** is a special kind of class member function. It defines a conversion that converts a value of a class type to a value of some other type.
- A conversion function must be a member function. The function may not specify a return type, and the parameter list must be empty.
- Conversion operations ordinarily should not change the object they are converting. As a result, conversion operators usually should be defined as `const` members.