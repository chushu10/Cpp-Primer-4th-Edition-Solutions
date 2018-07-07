# Exercise 4.8

Write a program to compare two arrays for equality. Write a similar program to compare two `vector`s.

**Answer**:

- Array equality:
    ```cpp
    #include <iostream>
    bool arrayEqual(int a[], int b[], size_t size) {
        for (size_t i = 0; i < size; i++) {
            if (a[i] != b[i]) {
                return false;
            }
        }
        return true;
    }

    int main()
    {
        int ia[5] = {1, 2, 3, 4, 5};
        int ia2[5] = {1, 2, 3, 4, 5};
        if (arrayEqual(ia, ia2, 5)) {
            std::cout << "ia and ia2 are equal" << std::endl;
        } else {
            std::cout << "ia and ia2 are not equal" << std::endl;
        }
        return 0;
    }
    ```
- `vector` equality:
    ```cpp
    #include <iostream>
    #include <vector>
    using std::vector;

    bool vectorEqual(vector<int> a, vector<int> b) {
        if (a.size() != b.size()) {
            return false;
        }
        for (vector<int>::iterator iter = a.begin(), iter2 = b.begin();
                                iter != a.end(); ++iter, ++iter2) {
            if (*iter != *iter2) {
                return false;
            }
        }
        return true;
    }

    int main()
    {
        vector<int> ivec = {1, 2, 3, 4, 5};
        vector<int> ivec2 = {1, 2, 3, 6, 5};
        if (vectorEqual(ivec, ivec2)) {
            std::cout << "ivec and ivec2 are equal" << std::endl;
        } else {
            std::cout << "ivec and ivec2 are not equal" << std::endl;
        }
        return 0;
    }
    ```