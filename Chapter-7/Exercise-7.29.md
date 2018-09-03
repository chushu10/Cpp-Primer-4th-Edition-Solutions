# Exercise 7.29

Which one of the following declarations and definitions would you put in a header? In a program text file? Explain why.

(a) `inline bool eq(const BigInt&, const BigInt&) {...}`
(b) `void putValues(int *arr, int size);`

**Answer**:

I will put (a) in a header, and (b) in a text file. Because `inline`s should be defined in header files. By putting the inline functions in headers, we ensure that the same definition is used whenever the function is called and that the compiler has the function definition available at the point of call.