# Exercise 6.2

What is a block? Give an example of when you might use a block.

**Answer**:

- What: a sequence of statements surrounded by a pair of curly braces.
- When: the rules of the language require a single statement, but the program's logic needs to execute more than once. Such as:

```cpp
if (cond1) {
    do_first_thing;
    do_second_thing;
    do_third_thing;
} else {
    ;// do nothing
}
```