# Exercise 7.22

Write the prototypes for each of the following functions:
(a) A function named `compare` with two parameters that are reference to a class named `matrix` and with a return value of type `bool`.
(b) A function named `change_val` that returns a `vector<int>` iterator and takes two parameters: one is an `int` and the other is an iterator for a `vector<int>`.

**Answer**:

(a)

```cpp
bool compare(matrix & , matrix & );
```

(b)

```cpp
vector<int>::iterator change_val(int , vector<int>::iterator );
```