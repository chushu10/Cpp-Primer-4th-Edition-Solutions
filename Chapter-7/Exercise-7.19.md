# Exercise 7.19

Indicate whether the following program is legal. If so, explain what it does; if not, make it legal and then explain it.

```cpp
int &get(int *arry, int index) { return arry[index]; }
int main() {
    int ia[10];
    for (int i = 0; i != 10; ++i) {
        get(ia, i) = 0;
    }
}
```

**Answer**:

It's valid, because the array `ia` exists before calling function `get`, so that its elements `ia[index]` are also pre-existing objects. When can safely return reference to the elements and set the value of them to 0, because a reference returned is an l-value.