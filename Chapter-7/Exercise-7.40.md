# Exercise 7.40

Is the following function call legal? If not, why is the call in error?

```cpp
enum Stat { Fail, Pass };
void test(Stat);
test(0);
```

**Answer**:

In error, because we cannot pass an integral value to a `enum` parameter. The compiler will complain:

```bash
error: invalid conversion from ‘int’ to ‘Stat’ [-fpermissive]
```