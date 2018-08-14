# Exercise 6.15

The `while` loop is particularly good at executing while some condition holds; for example, while the end-of-file is not reached, read a next value. The `for` loop is generally thought of as a step loop: An index steps through a range of values in a collection. Write an idiomatic use of each loop and then rewrite each using the other loop construct. If you were able to program with only one loop, which construct would you choose? Why?

**Answer**:

```cpp
// typical while use
while (some_condition) {
    // do something
}
```

```cpp
// typical for use
for (int i = 0; i < threshold; ++i) {
    // do something related to i
}
```

```cpp
// use while to do for's job
int i = 0
while (i < threshold) {
    // do something related to i
}
```

```cpp
// use for to do while's job
for(;some_condition;) {
    // do something
}
```

I would prefer `for` if I can only use one loop. Because the `for` statement is versatile, it can be easily transferred to a `while` loop. However, if we use `while` loop to do `for`'s job, we always have to use more statements, which is verbose.