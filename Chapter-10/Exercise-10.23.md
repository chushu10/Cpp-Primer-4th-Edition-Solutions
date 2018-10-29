# Exercise 10.23

Write a program that stores the excluded words in a `vector` instead of in a `set`. What are the advantages to using a `set`?

**Answer**:

```cpp
string word;
vector<string> excluded_words;
while (cin >> word) {
    vector<string>::iterator it = excluded_words.begin();
    for (; it != excluded_words.end(); ++it) {
        if (*it == word) {
            continue;
        }
    }
    excluded_words.push_back(word);
}
```

Using `set`, the program above can be as simple as this:

```cpp
string word;
set<string> excluded_words;
while (cin >> word) {
    excluded_words.insert(word);
}
```