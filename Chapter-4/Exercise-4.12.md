# Exercise 4.12

Given a pointer, `p`, can you determine whether `p` points to a valid object? If so, how? If not, why?

**Answer**:

The answer is "you can't". Because pointer is like the package of chocolate, you never know what flavor of chocolate lies behind. The only way to know whether `p` points to a valid object is to dereference it, which will always result in run-time error when `p` points to a invalid object.

BTW, you can determine whether `p` points to an object by comparing it to preprocessor variable `NULL`.