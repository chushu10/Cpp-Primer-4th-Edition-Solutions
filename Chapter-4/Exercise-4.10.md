# Exercise 4.10

Explain the rationale for preferring the first form of pointer declaration.

```cpp
int *ip; // good practice
int* ip; // legal but misleading
```

**Answer**:

Declaring pointer with * near the type makes us treat `int*` as type, while it it not. As the example below:

```cpp
int* ip, ip2;
```

We may treat `ip` and `ip2` both pointers, however only `ip` is a pointer, `ip2` is a `int` object. Using the declaration below will be more precise:

```cpp
int *ip, *ip2;
```