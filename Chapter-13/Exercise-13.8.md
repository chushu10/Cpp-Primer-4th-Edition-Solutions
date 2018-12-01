# Exercise 13.8

For each type listed in the second(It is "first" in the original book of C++ Primer 4th edition, but according to context, this should be the second exercise) exercise in Section 13.1.2 (p. 481 ) indicate whether the class would need an assignment operator.

**Answer**:

a. A `Point3w` class containing four `float` members(**Don't need an assignment operator, the synthesized one is enough**).
b. A `Matrix` class in which the actual matrix is allocated dynamically within the constructor and is deleted within its destructor(**Need one**).
c. A `Payroll` class in which each object is provided with a unique ID(**Need one**).
d. A `Word` class containing a `string` and a `vector` of line and column location pairs(**Don't need**).