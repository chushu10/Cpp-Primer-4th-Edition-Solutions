# Exercise 7.11

When should reference parameters be `const`? What problems might arise if we make a parameter a plain reference when it could be a `const` reference?

**Answer**:

Most of the time. See [Best Practices](BestPractices.md).

> Reference parameters that are not changed should be references to `const`). Plain, non`const` reference parameters are less flexible. Such parameters may not be initialized by `const` objects, or by any arguments that are literals or expression that yield r-values.