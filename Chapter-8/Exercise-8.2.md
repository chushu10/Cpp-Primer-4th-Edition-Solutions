# Exercise 8.2

The following declaration is in error. Identify and correct the problem(s):

`ostream print(ostream os);`

**Answer**:

The library types do not allow copy, so that we cannot have a parameter or return type that is one of the stream types. Instead, use reference:

```cpp
ostream &print(ostream &os);
```