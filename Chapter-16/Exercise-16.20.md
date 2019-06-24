# Exercise 16.20

What happens during template argument deduction?

**Answer**:

The compiler determines the types and values of the template arguments from the type of the function arguments by the following rules:

1. Multiple type parameter arguments must match exactly.
2. There are limited conversions on type parameter arguments.
3. Normal conversions only apply for nontemplate arguments.
4. The type of the parameters in a function pointer determines the type of the template arguments. *It is an error if the template arguments cannot be determined from the function pointer type.*
