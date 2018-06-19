# Exercise 3.16

List three ways to define a `vector` and give it 10 elements, each with the value 42. Indicate whether there is a preferred way to do so and why.

**Answer**:

1. Through constructor:
    ```cpp
    vector<int> ivec(10, 42);
    ```
2. By for loop:
    ```cpp
    vector<int> ivec;
    for (int i = 0; i < 10; ++i) {
        ivec.push_back(42);
    }
    ```
3. By for loop but allocate memory first:
    ```cpp
    vector<int> ivec(10); // all 10 elements are initialized to 0
    for (vector<int>::size_type ix = 0; ix != ivec.size(); ++ix) {
        ivec[ix] = 42;
    }
    ```

Absolutely, in this case the number 1 method is the most precise and efficient way. However, for flexibility(not all the elements should be exactly 42), method number 2 can be taken. Anyway, you shouldn't use method number 3 because it's neither efficient nor flexible, adding the 11th element to the `vector` may result in heavy overhead.