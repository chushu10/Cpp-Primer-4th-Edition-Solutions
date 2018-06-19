# Exercise 3.15

Is the following program legal? If not, how might you fix it?

```cpp
vector<int> ivec;
ivec[0] = 42;
```

**Answer**: It's illegal, you can't use subscription to refer an non-existing element. One proper fixation is:

```cpp
vector<int> ivec;
ivec.push_back(42);
```