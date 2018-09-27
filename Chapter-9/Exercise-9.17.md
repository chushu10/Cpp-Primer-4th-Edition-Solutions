# Exercise 9.17

What type should be used to read the elements in a list of `string`s?

**Answer**:

`list<string>::const_iterator`

Example:

```cpp
list<string> slist;
// ...
// Use const_iterator to read
list<string>::const_iterator it = slist.begin();
for ( ; it != slist.end(); ++it) {
    cout << *it << endl;
}
```