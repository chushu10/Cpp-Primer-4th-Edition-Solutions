# Exercise 6.3

Use the comma operator (Section 5.9, 168) to rewrite the `else` branch in the `while` loop from the bookstore problem so that it no longer requires a block. Explain whether this rewrite improves or diminishes the readability of this code.

**Answer**:

```cpp
// original
while (std::cin >> trans)
    if (total.same_isbn(trans))
        total = total + trans;
    else {
        std::cout << total << std::endl;
        total = trans;
    }
```

```cpp
// rewrite
while (std::cin >> trans)
    if (total.same_isbn(trans))
        total = total + trans;
    else
        std::cout << total << std::endl; total = trans;
```

Absolutely diminishes readability.