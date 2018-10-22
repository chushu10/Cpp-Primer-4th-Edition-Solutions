# Exercise 10.10

What does the following program do?

```cpp
map<int, int> m;
m[0] = 1;
```

Contrast the behavior of the previous program with this one:

```cpp
vector<int> v;
v[0] = 1;
```

**Answer**:

First program:

1. Create an empty `map` from `int` to `int`.
2. Search the map for key `0`, which is not found.
3. Create a key-value pair with key of `0` and value initialized to `0`.
4. Insert the key-value pair into the `map`.
5. Change the value of the pair to `1`.

Second program:

1. Create an empty `vector` of `int`.
2. Insert to the last position a element with value `1`.