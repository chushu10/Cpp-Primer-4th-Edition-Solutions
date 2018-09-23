# Exercise 9.2

Show an example of each of the four ways to create and initialize a `vector`. Explain what values each `vector` contains.

**Answer**:

| Methods | Explainations |
| :------ | :------------ |
| vector<T> c; | Create an empty vector named c. |
| vector c(c2); | Create c as a copy of vector c2. |
| vector c(b, e); | Create c with a copy of the elements from the range denoted by iterators b and e. |
| vector c(n, t); | Create c with n elements, each with value t. |
| vector c(n); | Create c with n value-initialized elements. |