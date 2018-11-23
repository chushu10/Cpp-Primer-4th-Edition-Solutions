# Exercise 12.30

Compile the following code:

```cpp
f(const vector<int>&);
int main() {
    vector<int> v2;
    f(v2); // should be ok
    f(42); // should be an error return 0;
}
```

What can we infer about the `vector` constructors based on the error on the second call to `f`? If the call succeeded, then what would you conclude?

**Answer**:

I got the error output as below:

```bash
ex1230.cc:8:5: error: no matching function for call to 'f'
    f(42); // should be an error
    ^
ex1230.cc:4:6: note: candidate function not viable: no known conversion from 'int' to 'const vector<int>' for 1st argument
void f(const vector<int>&);
     ^
1 error generated.
```

It suggests that there is no constructor of `vector` that takes only an `int` type.