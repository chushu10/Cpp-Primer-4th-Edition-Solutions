# Best Practices

Here are the best practices listed in chapter 7:

- Reference parameters that are not changed should be references to `const`. Plain, non`const` reference parameters are less flexible. Such parameters may not be initialized by `const` objects, or by any arguments that are literals or expression that yield r-values.
- Ordinarily, functions should not have `vector` or other library container parameters. Calling a function that has a plain, non-reference `vector` parameter will **copy every element** of the `vector`.
- It is usually a good idea to define array parameters as pointers, rather than using the array syntax. Doing so makes it clear that what is being operated on is a pointer to an array element, not the array itself. Because an array dimension is ignored, including a dimension in a parameter definition is particularly **misleading**. (When the compiler checks an argument to an array parameter, it checks only that the argument is a pointer and that the type of the pointer and the array elements match. The size of the array is not checked.)
- Functions that do not change the elements of their array parameter should make the parameter a pointer to `const`: `void f(const int*) { /* ... */}`
- **Never return a reference/pointer to a local object.** Because when a function completes, the storage in which the local objects were allocated is freed. A reference/pointer to a local object refers to **undefined** memory after the function terminates.
- Function prototypes provide the **interface** between the programmer who defines the function and programmers who use it. When we use a function, we **program to the function's prototype**.
- A `const` object or a pointer or reference to a `const` object may be used to call only `const` member functions. It is an error to try to call a non`const` member function on a `const` object or through a pointer or reference to a `const` object. Thus, the following code is in error:

```cpp
const Sales_item total; // init object total
const Sales_item &rtotal = total;
const Sales_item *ptotal = &total;
total.someNonConstMemberFunc(); // error: cannot call non-const member function on const object
rtotal.someNonConstMemberFunc(); // error: cannot call non-const member function on reference to const object
ptotal->someNonConstMemberFunc(); // error: cannot call non-const member function on pointer to const object
```

- Functions cannot be overloaded based only on differences in the return type.
- A function that takes a `const` reference is different from on that takes a non`const` reference. Similarly, a function that takes a pointer to a `const` type differs from a function that takes a pointer to the non`const` object of the same type.
- In general, it is a bad idea to declare a function locally. Function declarations should go in **header files**.
- In C++, name lookup happens before type checking.