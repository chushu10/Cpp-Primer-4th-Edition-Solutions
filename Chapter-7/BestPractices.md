# Best Practices

Here are the best practices listed in chapter 7:

- Reference parameters that are not changed should be references to `const`. Plain, non`const` reference parameters are less flexible. Such parameters may not be initialized by `const` objects, or by any arguments that are literals or expression that yield r-values.
- Ordinarily, functions should not have `vector` or other library container parameters. Calling a function that has a plain, non-reference `vector` parameter will copy every element of the `vector`.