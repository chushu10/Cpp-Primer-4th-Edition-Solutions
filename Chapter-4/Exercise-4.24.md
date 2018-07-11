# Exercise 4.24

Explain the differences between `strcpy` and `strncpy`. What are the advantages of each? The disadvantage?

**Answer**:

|           | Advantages | Disadvantages |
| :-------: | :--------- | :------------ |
| `strcpy`  | Easier to use | Should calculate the `dst` char array carefully. Otherwise, may result in severe buffer overflow error. |
| `strncpy` | A little bit safer | Still should calculate the copied length carefully, but truncating is safer than overrunning the array. |

Both functions are error prone, not recommend to use. Instead, use APIs of C++ library `string`.