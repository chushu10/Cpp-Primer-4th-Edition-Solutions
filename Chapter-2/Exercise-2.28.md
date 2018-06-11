# Exercise 2.28

Compile the following program to determine whether your compiler warns about a missing semicolon after a class definition:

```cpp
class Foo {
    // empty
} // Note: no semicolon
int main()
{
    return 0;
}
```

If the diagnostic is confusing, remember the message for future reference.

**Answer**: Used [online compiler](https://www.onlinegdb.com/online_c_compiler) to get the following results:

```bash
 main.cpp:12:1: error: expected ';' after class definition
 } // Note: no semicolon
 ^
```