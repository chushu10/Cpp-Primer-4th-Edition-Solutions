# Exercise 5.24

The program in this section is similar to the program on page 163 that added elements to a `vector`. Both programs decremented a counter to generate the element values. In this program we used the prefix decrement and the earlier one used postfix. Explain why we used prefix in one and postfix in the other.

**Answer**:

```cpp
// This program
int cnt = ivec.size();
// add elements from size...1 to ivec
for (vector<int>::size_type ix = 0;
                 ix != ivec.size(); ++ix, --cnt) {
    ivec[ix] = cnt;
}
```

```cpp
// Previous program
int cnt = 10;
// add elements from 10...1 to ivec
while (cnt > 0) {
    ivec.push_back(cnt--);
}
```

Both the programs add elements from X...1 to `ivec`, no matter what X is. In this program, the decrement operator is applied on the operand in the end of for loop, so it doesn't matter the decrement operator is prefix or postfix. But to be more **efficient**, prefix version was chosen; However, in the previous program, we want to add the older version of `cnt` to `ivec`, so the postfix version was chosen.

