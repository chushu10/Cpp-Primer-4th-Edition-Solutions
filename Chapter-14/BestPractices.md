# Best Practices

- Generally, output operators should print the contents of the object, with minimal formatting. They should not print a newline.
- IO operators usually read or write the non`public` data members. As a consequence, classes often make the IO operators `friend`s.
- Ordinarily, the relational operators, like the equality operators, should be defined as nonmember functions.
- The overloaded arrow operator must return either a pointer to a class type or an object of a class type that defines its own operator arrow.