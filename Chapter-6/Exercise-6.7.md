# Exercise 6.7

There is one problem with our vowel-counting program as we've implemented it: It doesn't count capital letters as vowels. Write a program that counts both lower- and uppercase letters as the appropriate vowel--that is, your program should count both 'a' and 'A' as part of `aCnt`, and so forth.

**Answer**:

```cpp
int vowelCnt = 0;
// ...
switch (ch)
{
    case 'a': case 'e': case 'i': case 'o': case 'u':
    case 'A': case 'E': case 'I': case 'O': case 'U':
        ++vowelCnt;
        break;
}
```