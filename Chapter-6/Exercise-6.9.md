# Exercise 6.9

Modify our vowel-count program so that it counts the number of occurrences of the following two-character sequences: `ff`, `fl`, adn `fi`.

**Answer**:

```cpp
int cnt = 0;
// ...
switch (ch)
{
    case 'f':
        switch (next_ch)
        {
            case 'f':
                ff++;
                break;
            case 'l':
                fl++;
                break;
            case 'i':
                fi++;
                break;
        }
        break;
}
```