# Exercise 10.2

There are at least three ways to create the `pair`s in the program for the previous exercise. Write three versions of the program creating the `pair`s in each way. Indicate which form you think is easier to write and understand and why.

**Answer**:

```cpp
// version one
pair<string, int> strIntPair;
vector< pair<string, int> > pairVec;
while (cin >> strIntPair.first >> strIntPair.second) { // directly access members
    pairVec.push_back(strIntPair);
}
```

```cpp
// version two
pair<string, int> strIntPair;
string first;
int second;
vector< pair<string, int> > pairVec;
while (cin >> first >> second) {
    strIntPair = make_pair(first, second); // use make_pair
    pairVec.push_back(strIntPair);
}
```

```cpp
// version three
pair<string, int> strIntPair;
string first;
int second;
vector< pair<string, int> > pairVec;
while (cin >> first >> second) {
    strIntPair = pair<string, int>(first, second); // use constructor
    pairVec.push_back(strIntPair);
}
```

For me, version one is absolutely the easiest to write and understand and at the same time the most simple. Because you don't have to declare the member types before hand. Just visiting the `pair` member makes the code clean and easy to understand.