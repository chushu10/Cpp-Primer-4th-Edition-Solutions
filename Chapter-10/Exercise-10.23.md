# Exercise 10.23

Write a program that stores the excluded words in a `vector` instead of in a `set`. What are the advantages to using a `set`?

**Answer**:

```cpp
string word;
vector<string> excludedWords;
while (cin >> word) {
    vector<string>::iterator it = excludedWords.begin();
    for (; it != excludedWords.end(); ++it) {
        if (*it == word) {
            continue;
        }
    }
    exludedWords.push_back(word);
}
```

Using `set`, the program above can be as simple as this:

```cpp
string word;
set<string> excludedWords;
while (cin >> word) {
    excludedWords.insert(word);
}
```