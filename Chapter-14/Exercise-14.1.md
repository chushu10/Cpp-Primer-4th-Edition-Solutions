# Exercise 14.1

In what ways does an overloaded operator differ from a built-in operator? In what ways are overloaded operators the same as the built-in operators?

**Answer**:

Difference: The meaning of an operator for the built-in types may not be changed. An overloaded operator must have at least one operand of class or enumeration (Section 2.7 , p. 62 ) type.

Common: An overloaded operator has the same precedence and associativity as the corresponding built-in operator.