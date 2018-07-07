# Exercise 4.7

Write the code necessary to assign one array to another. Now, change the code to use `vector`s. How might you assign one `vector` to another?

**Answer**:

- Array copy:
    ```cpp
    const size_t array_size = 10;
    int ia[array_size];
    int ia1[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    for (size_t ix = 0; ix < array_size; ++ix) {
        ia[ix] = ia1[ix];
    }
    ```
- `vector` copy:
    ```cpp
    vector<int> ivec;
    vector<int> ivec1 = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    for (vector<int>::iterator iter = ivec1.begin();
                               iter != ivec1.end(); ++iter) {
        ivec.push_back(*iter);
    }
    ```