# Exercise 2.20

Given the following program fragment, what values are printed?

```cpp
int i = 100, sum = 0;
for (int i = 0; i != 10; ++i)
    sum += i;
std::cout << i << " " << sum << std::endl;
```

**Answer**: "10 45", because the statement scope `i` hides the definition of outer scope `i`, and `i` will iterate through 0 to 10, that means `sum` = (1 + 9) * 9 / 2 = 45.