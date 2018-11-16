# Exercise 12.14

It is legal but redundant to refer to members through the `this` pointer. Discuss the pros and cons of explicitly using the this pointer to access members.

**Answer**:

- Pros: we can write member function as below:
    ```cpp
    void set(int val)
    {
        this->val = val;
    }
    ```
- Cons: redundant.