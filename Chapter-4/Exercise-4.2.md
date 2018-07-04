# Exercise 4.2

What are the values in the following arrays?

```cpp
string sa[10];
int ia[10];
int main() {
    string sa2[10];
    int    ia2[10];
}
```

**Answer**:

- All the elements of array `sa` and `sa2` are empty string "", because no matter the `string` array is defined in function or outside of function, a `string` type has a default constructor which will initialize its value to empty string;
- Elements of `ia` are all zeros, because `ia` is defined outside of function.
- Elements of `ia2` are undefined, because `ia2` is defined inside of function and built-in type `int` has no default constructor;
