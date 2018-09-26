# Exercise 9.14

Using iterators, write a program to read a sequence of `string`s from the standard input into a `vector`. Print the elements in the `vector`.

**Answer**:

```cpp
int main(int argc, char const *argv[])
{
    vector<string> svec(10);
    vector<string>::iterator first = svec.begin();
    vector<string>::iterator last = svec.end();
    while (first != last) {
        cin >> *first++;
    }
    vector<string>::const_iterator it = svec.begin();
    for ( ; it != last; ++it) {
        cout << *it << " ";
    }
    cout << endl;
    return 0;
}
```