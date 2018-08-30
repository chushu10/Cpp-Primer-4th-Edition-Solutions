# Best Practices

Here are the best practices listed in chapter 7:

- Reference parameters that are not changed should be references to `const`. Plain, non`const` reference parameters are less flexible. Such parameters may not be initialized by `const` objects, or by any arguments that are literals or expression that yield r-values.
- Ordinarily, functions should not have `vector` or other library container parameters. Calling a function that has a plain, non-reference `vector` parameter will **copy every element** of the `vector`.
- It is usually a good idea to define array parameters as pointers, rather than using the array syntax. Doing so makes it clear that what is being operated on is a pointer to an array element, not the array itself. Because an array dimension is ignored, including a dimension in a parameter definition is particularly **misleading**. (When the compiler checks an argument to an array parameter, it checks only that the argument is a pointer and that the type of the pointer and the array elements match. The size of the array is not checked.)
- Functions that do not change the elements of their array parameter should make the parameter a pointer to `const`: `void f(const int*) { /* ... */}`
- **Never return a reference/pointer to a local object.** Because when a function completes, the storage in which the local objects were allocated is freed. A reference/pointer to a local object refers to **undefined** memory after the function terminates.
- Function prototypes provide the **interface** between the programmer who defines the function and programmers who use it. When we use a function, we **program to the function's prototype**.