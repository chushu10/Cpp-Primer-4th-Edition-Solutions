# Exercise 10.2

There are at least three ways to create the `pair`s in the program for the previous exercise. Write three versions of the program creating the `pair`s in each way. Indicate which form you think is easier to write and understand and why.

**Answer**:

```cpp
// version one
pair<string, int> str_int_pair;
vector< pair<string, int> > pair_vec;
while (cin >> str_int_pair.first >> str_int_pair.second) { // directly access members
    pair_vec.push_back(str_int_pair);
}
```

```cpp
// version two
pair<string, int> str_int_pair;
string first;
int second;
vector< pair<string, int> > pair_vec;
while (cin >> first >> second) {
    str_int_pair = make_pair(first, second); // use make_pair
    pair_vec.push_back(str_int_pair);
}
```

```cpp
// version three
pair<string, int> str_int_pair;
string first;
int second;
vector< pair<string, int> > pair_vec;
while (cin >> first >> second) {
    str_int_pair = pair<string, int>(first, second); // use constructor
    pair_vec.push_back(str_int_pair);
}
```

For me, version one is absolutely the easiest to write and understand and at the same time the most simple. Because you don't have to declare the member types before hand. Just visiting the `pair` member makes the code clean and easy to understand.