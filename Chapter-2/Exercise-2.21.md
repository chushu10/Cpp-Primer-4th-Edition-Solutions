# Exercise 2.21

Is the following program legal?

```cpp
int sum = 0;
for (int i = 0; i != 10; ++i)
    sum += i;
std::cout << "Sum from 0 to " << i
          << " is " << sum << std::endl;
```

**Answer**: It is illegal, because the variable `i` is not defined in the scope out of `for` loop, that you can't print it by `std::cout`.