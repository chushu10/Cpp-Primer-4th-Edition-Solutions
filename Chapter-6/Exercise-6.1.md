# Exercise 6.1

What is a null statement? Give an example of when you might use a null statement.

**Answer**:

- What: an empty statement.
- When: the language requires a statement but the program's logic does not. Such as:

```cpp
if (cond1) {
    do_something;
} else if (cond2) {
    do_something;
} else {
    ; // do nothing
}
```