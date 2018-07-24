# Exercise 5.4

Define the term overflow. Show three expressions that will overflow.

**Answer**:

Overflow: A value is computed that is too large for its type.

Example 1:

```cpp
short short_value = 32767;
short_value += 1; // short_value = -32768
```

Example 2:

```cpp
signed char signed_char = 127;
signed_char += 1; // signed_char = -128
```

Example 3:

```cpp
char a_char = 127;
a_char += 1; // signed_char = -128
```