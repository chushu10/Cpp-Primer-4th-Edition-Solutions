# Exercise 2.27

What does the following code print?

```cpp
int i, &ri = i;
i = 5; ri = 10;
std::cout << i << " " << ri << std::endl;
```

**Answer**: It prints `10 10`, because the value of `i` is changed by the assignment of `ri = 10;`