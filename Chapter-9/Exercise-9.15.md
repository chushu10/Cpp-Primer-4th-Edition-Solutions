# Exercise 9.15

Rewrite the program from the previous exercise to use a `list`. List the changes you needed to change the container type.

**Answer**:

```cpp
// Just have to change 4 lines, each line is switching vector to list
int main(int argc, char const *argv[])
{
    list<string> svec(10); // vector -> list
    list<string>::iterator first = svec.begin(); // vector -> list
    list<string>::iterator last = svec.end(); // vector -> list
    while (first != last) {
        cin >> *first++;
    }
    list<string>::const_iterator it = svec.begin(); // vector -> list
    for ( ; it != last; ++it) {
        cout << *it << " ";
    }
    cout << endl;
    return 0;
}
```