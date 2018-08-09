# Exercise 6.8

Modify our vowel-counting program so that it also counts the number of blank spaces, tabs, and newlines read.

**Answer**:

```cpp
int cnt = 0;
// ...
switch (ch)
{
    case 'a': case 'e': case 'i': case 'o': case 'u':
    case 'A': case 'E': case 'I': case 'O': case 'U':
    case ' ': case '\t': case '\n':
        ++cnt;
        break;
}
```