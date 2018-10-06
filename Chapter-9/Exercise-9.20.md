# Exercise 9.20

Write a program to compare whether a `vector<int>` contains the same elements as a `list<int>`.

**Answer**:

```cpp
vector<int> ivec;
list<int> ilist;
// filling elements in ivec and ilist
// method 1: directly compare the elements of ivec and ilist
vector<int>::const_iterator it1 = ivec.begin();
list<int>::const_iterator it2 = ilist.begin();
while (it1 != ivec.end() && it2 != ilist.end()) {
    if (*it1 < *it2) {
        cout << "ivec is less than ilist" << endl;
        return;
    } else if (*it1 > *it2) {
        cout << "ivec is greater than ilist" << endl;
        return;
    } else {
        ++it1;
        ++it2;
    }
}
cout << "ivec is equal than ilist" << endl;
```

```cpp
// method2: first convert ilist to vector, then compare them using relational operator
vector<int> ivec2;
for ( ; it2 != ilist.end(); ++it2) {
    ivec2.push_back(*it2);
}
if (ivec < ivec2) {
    cout << "ivec is less than ilist" << endl;
} else if (ivec > ivec2) {
    cout << "ivec is greater than ilist" << endl;
} else {
    cout << "ivec is equal than ilist" << endl;
}
```