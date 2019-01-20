# Exercise 14.41

Explain the difference between these two conversion operators:

```cpp
class Integral {
public:
    operator const int();
    operator int() const;
};
```

Are either of these conversions too restricted? If so, how might you make the conversion more general?

**Answer**:

I don't know what `operator const int();` mean. However, the `operator int() const;` one is the correct way to define a `int` conversion, it is not restricted.