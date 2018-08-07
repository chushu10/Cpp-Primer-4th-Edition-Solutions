# Exercise 6.4

In the `while` loop that solved the bookstore problem, what effect, if any, would removing the curly brace following the `while` and its corresponding close curly have on the program?

**Answer**:

```cpp
while (std::cin >> trans)
    if (total.same_isbn(trans))
        total = total + trans;
    else //{ remove curly
        std::cout << total << std::endl;
        total = trans; // outside of while loop
    //} remove close curly
```

Statement `total = tran;` would be treated outside of the `while` loop.