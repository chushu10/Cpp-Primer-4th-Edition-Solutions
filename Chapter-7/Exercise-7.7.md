# Exercise 7.7

Explain the differences in the following two parameter declarations:

`void f(T);`
`void f(T&);`

**Answer**:

The first one declares the parameter to a plain object, which results in copying the object when calling the function `f`; The second one declares the parameter to a reference to an object, which will not copy the object when calling the function `f`.